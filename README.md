# StreammingTest
Access and stream web camera in **nodejs** using **ffmpeg**, **websockets** and **HTML5**.

### **Using



$ cd streaminTest

$ npm install

$ npm run express-server
(Web server - node index.js)
	
$ npm run streaming-server
(Web Sockets - node stream.js <secretKey>)
	
$ ffmpeg run the following command on a terminal :
/// mine 

ffmpeg -y -rtbufsize 100M -f vfwcap -video_size 640x480 -framerate 24 -i video="Integrated Webcam":audio="Microphone Array (Technologie Intel® Smart Sound)" vidTest.mp4 -movflags faststart -framerate 15 -vcodec mpeg1video -preset veryfast -maxrate 3000k -bufsize 4000k -c:a aac -b:a 160k -ar 44100 -b:a 128k -f mpeg1video http://localhost:8082/12345/640/480

// in general 
ffmpeg -f dshow -i video="<cameraDeviceName>":audio="<audioDeviceName>" <outputName>.mp4 -f mpeg1video http://localhost:<webSocketsStreamingPort>/<secretKey>/<width>/height



### **Third Party Libraries:**
  * **ExpressJs** http://expressjs.com/
  * **Ws** https://www.npmjs.com/package/ws
  *  **JsMpg** *(MPEG1 Video Decoder in JavaScript)* https://libraries.io/bower/jsmpg 

### **Requirements**

  * **NodeJs** https://nodejs.org/
  * **ffmpeg** https://www.ffmpeg.org/

