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
        stage('continuous Deploy')
        {
            steps
            {
                script
                {
                    cicd.deploy("Multibranch","172.31.46.229","testapp")
                }
            }
        }
        stage('continuous Test')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("Functiontesting")
                    cicd.runselenium("Multibranch")
                }
            }
        }
        stage('continuous delivery')
        {
            steps
            {
                script
                {
                    cicd.deploy("Multibranch","172.31.38.218","prod")
                }
            }
        }
    }
}
