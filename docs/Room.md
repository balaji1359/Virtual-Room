# Virtual Rooom *0.1.0*

### src/room.js


#### addPauseListener() 

Adds the pause Listener to the stream. Used in Synchronized playback, enabling pause event to work smooth






##### Returns


- `Void`



#### addPlayListener() 

Adds the play Listener to the stream and deletes all previous `paused` toasts. Used in Synchronized playback, enabling play event to work smooth






##### Returns


- `Void`



#### connectSignalServer()

Adds/verifies the current room of the peer on signalling server. Adds the current peer to the room if the room is added/verified





##### Returns


- `Void`



#### handleMessage()

To handle and direct the messages received from the server other than messages related to connection of peers





##### Returns


- `Void`



#### copyBroadcastURL()

Selects the range of the Room URL and copies it to the clipboard





##### Returns

- `Void`



#### generateURL()

Logic for generating URL, sets the Room URL text to the new URL






##### Returns

- `Void`



#### fragmentMP4()

Pre Initiation for fragmenting of MP4 video, adds the event Listener to set mimeCodec of MediaSource and calls the onFragment() function





##### Returns

- `Void`



#### setSourceBuffer()

Configures the media Source, adds source buffer according to the video's codecs. Sets the segmentIndex, AppendMode and simple mode





##### Returns

- `Void`



#### onFragment()

Initializes the file reader(reads the video file), initializes MP4Box and segmentation of the video. Reads the video file information and accordingly changes `nbSamples`, `numChunks`, `mimeCodec` and more. Also tells if the codec is supported or not. Finally fragments the video into small chunks and sends them to append in media source and to other peers




##### Returns

- `Void`



#### preInititiation()

Initializes connection with the signalling Server and adds User media to local window stream. Sets currentPeer





##### Returns

- `Void`



#### fallbackUserMedia()

Callback for failure of `getUserMedia`. Replaces the empty video element with a default avatar





##### Returns

- `Void`



#### initiatePeerConnection(currentPeer, callback)

Initiates the `RTCPeerConnection` and negotiation with other peers. Calls createDataChannel() to initiate data channel connection



##### Parameters

| Name        | Type | Description |
| ------------| ---- | ----------- |
| currentPeer | `Object`  | - Server ID of the peer for peer Connection |
| callback    | `Function`  | - To initialize data Channel |





##### Returns

- `Void`



#### sendOffer()

Sends the offer to other peers on negotiation





##### Returns

- `Void`



#### createLocalDescription(answer)

Sets the localDescription and sends the offer to the `currentPeer`



##### Parameters

| Name        | Type | Description |
| ------------| ---- | ----------- |
| answer | `Object`  | - Answer from `currentPeer` |





##### Returns

- `Void`


#### gotMessageFromServer(message)

Used to handle all the messages from peers regarding peer connections, data channel and video conference handling



##### Parameters

| Name        | Type | Description |
| ------------| ---- | ----------- |
| messages | `Object`  | - Message received from signalling Server |





##### Returns

- `Void`




#### cleanBuffer(chunkStart, chunkEnd)

Used to delete saved buffer from the browser and clean up `sourceBuffer`



##### Parameters

| Name        | Type | Description |
| ------------| ---- | ----------- |
| chunkStart | `Object`  | - start time of the chunk to be cleaned |
| chunkEnd | `Object`  | - end time of the chunk to be cleaned |





##### Returns

- `Void`




#### createDataChannel(currentPeer, callback)

Used to create data channel with `currentPeer`





##### Parameters

| Name        | Type | Description |
| ------------| ---- | ----------- |
| currentPeer | `Object`  | - current peer in peerConnections |
| callback | `function`  | - to set up channel |





##### Returns

- `Void`



#### sendChunk(chunk)

Sends the chunk to the appropriate peer using round robin method





##### Parameters

| Name        | Type | Description |
| ------------| ---- | ----------- |
| chunk | `Object`  | - fragmented chunk to be sent |





##### Returns

- `Void`