def attachments = [
  [
    text: 'I find your lack of faith disturbing!',
    fallback: 'Hey, Vader seems to be mad at you.',
    color: '#ff0000'
  ]
]
def slackResponse = slackSend(channel: "#pipeline-breaking-news", attachments: attachments)

pipeline {
    
    agent any
    
    stages{
        stage('Clone from Github') {
            steps {
                git branch: 'master', url:'https://github.com/AHMADSK1997/Breaking-News.git'
            }
        }
        stage('Build the Code') {
            steps{
                sh "./gradlew build"
            }
        }
        stage('Run'){
            steps{
                sh 'JENKINS_NODE_COOKIE=dontkill java -jar ./build/libs/BreakingNews-0.0.1-SNAPSHOT.jar &'
            }
        }
        stage('Send Slack'){
            steps {
                slackSend(channel: slackResponse.channelId, message : 'The app is running', timestamp: slackResponse.ts)
            }
        }
    }
}