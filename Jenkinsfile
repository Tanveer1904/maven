pipeline
{
    agent any
    stages
    {
        stage('Cdownl')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('Conbuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Contdep')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '77679e0f-dbe5-4d78-a2a7-2ada8f28f21d', path: '', url: 'http://172.31.21.108:8080')], contextPath: 'testapp', war: '**/*.war'
            }
        }
        stage('CTest')
        {
            steps
            {
                 git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                 
            }
        }
        stage('ConDel')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '77679e0f-dbe5-4d78-a2a7-2ada8f28f21d', path: '', url: 'http://172.31.30.230:8080')], contextPath: 'prodapp', war: '**/*.war'
            }
        }
        
    }
}
