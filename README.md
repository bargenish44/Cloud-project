## Big Data:

Call center on web which is written using MVC design pattern, and includes three systems:

<img src="https://github.com/bargenish44/Cloud-project/blob/master/Pictures/System%20architecture.png?raw=true" width="800" />


1) CallCenterInputSystem - Node.js EXPRESS server which serves a JS, EJS (using EJS view engine) & CSS  UI for "answering (reciving) calls", all clients are updated in real time using socketIO, this system is used to create the data, this data is then passed to KAFKA message broker which is hosted on cloudkarafka cloud, the data is passed to two KAFKA topics - Mongo and Redis.

<img src="https://github.com/bargenish44/Cloud-project/blob/master/Pictures/sender.JPG?raw=true" width="600" />

2) RedisSystem - Node.js EXPRESS server which recives data from KAFKA (CallCenterInputSystem), stores it in REDIS which runs in a Docker container, and serves a NRT 24-hour dashboard (using chart.js graphing library), updated in read time using SocketIO.

<img src="https://github.com/bargenish44/Cloud-project/blob/master/Pictures/dashboard.JPG?raw=true" width="600" />

<img src="https://github.com/bargenish44/Cloud-project/blob/master/Pictures/dashboard-city-topic-lang.JPG?raw=true" width="600" />

3) MongoSystem - recives data from KAFKA (CallCenterInputSystem) at mongo topic, stores it in Mongo which is hosted on Mongodb atlas cloud.

<img src="https://github.com/bargenish44/Cloud-project/blob/master/Pictures/mongo.JPG?raw=true" width="600" />
