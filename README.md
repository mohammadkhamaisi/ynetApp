# ynetApp
ynetApp is a java Application (Managed by Gradle) thats Reads the news from ynet site.

when you connect to your web app, the appliication read from xml file http://www.ynet.co.il/Integration/StoryRss2.xml and build an html table that view the news that the application read.
## Running ynetApp locally

```
git clone https://github.com/mohammadkhamaisi/ynetApp.git
cd ynetApp
./gradlew build
java -jar ./build/libs/ynetApp-0.0.1-SNAPSHOT.jar
```

we can find the html file here on port 8081: http://localhost:8081/


