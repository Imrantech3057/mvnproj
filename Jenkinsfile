pipeline
{
    agent any
    stages
    {
        stage('continuous Download')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("mvn")
                }
            }
        }
        stage('continuous Build')
        {
            steps
            {
                script
                {
                    cicd.mavenBuild()
                }
            }
        }
    }
}
