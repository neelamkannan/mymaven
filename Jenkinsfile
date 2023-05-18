pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
	 stage('continous deploy')
        {
            steps{
                deploy adapters: [tomcat9(credentialsId: 'd4f4e493-2098-4473-ac94-fb2ca43e4701', path: '', url: 'http://172.31.28.46:8080')], contextPath: 'qaapp', war: '**/*.war'
            }
      
    }
    
}    


