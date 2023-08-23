# go-mysql-example
## TableMapEvent
```mermaid
sequenceDiagram
    main ->> BinlogStreamer.ch: BinlogSyncer.NewBinlogSyncer
    main ->> BinlogSyncer.onStream: BinlogSyncer.onStream
    par
        note over BinlogSyncer.onStream: BinlogSyncer.parseEvent
        note over BinlogSyncer.onStream: BinlogParser.Parse
        note over BinlogSyncer.onStream: BinlogParser.ParseHeader
        note over BinlogSyncer.onStream: BinlogParser.ParseEvent
        BinlogSyncer.onStream ->> BinlogStreamer.ch: BinlogEvent 
    and
        note over main: BinlogStreamer.GetEvent
        BinlogStreamer.ch ->> main: BinlogEvent
    end
```

BinlogSyncer.NewBinlogSyncer

BinlogSyncer.StartSync
BinlogSyncer.startDumpStream
ㄴ BinlogSyncer.onStream 

BinlogStreamer.GetEvent

BinlogSyncer.parseEvent
BinlogParser.Parse


