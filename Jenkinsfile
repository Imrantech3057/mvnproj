node('built-in') 
{
    stage('download')
    {
        git 'https://github.com/Imrantech3057/mvnproj.git'
    }
    stage('build')
    {
        sh 'mvn package'
    }
    stage('deploy')
    {
        deploy adapters: [tomcat9(credentialsId: 'c7ce6b24-94d8-4a54-ba48-62d2d94a8a3c', path: '', url: 'http://172.31.25.75:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage('test')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /var/lib/jenkins/workspace/ScriptedPipeline/testing.jar'
    }
    stage('delivery')
    {
        deploy adapters: [tomcat9(credentialsId: 'c7ce6b24-94d8-4a54-ba48-62d2d94a8a3c', path: '', url: 'http://172.31.26.238:8080')], contextPath: 'prodapp', war: '**/*.war'
    }
}
