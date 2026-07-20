pipeline{

    agent any
    stages('Checkout')
    {
        steps{
            git brach: "main"
            // url of your github repo
            url:'https://github.com/shivam86200/jenkin-website.git'
        }
    }
    stage('Test')
    {
        steps{
            sh 'test -f index.html'
            echo 'Application file index.html found'
        }
    }
    post{
        success{
            echo 'Pipeline completed successfully!'
        }
        failure{
            echo'Pipeline failed!'
        }
    }
    
}