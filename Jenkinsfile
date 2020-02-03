pipeline {
    // master executor should be set to 0
    agent any
    stages {
	stage("Start Grid"){
	    steps{
		bat "docker-compose -f docker-compose.yaml up"
            }
        }
        stage("Grid Wait") {
            steps {
                //sh
                bat "timeout 30"
            }
        }
	stage("Test Case Exeution") {
	    steps {
                bat "Run.bat -run -project_location "C:\Users\DockerHost\dockercompose1\workspace\CITS_SAMPLE_JOB1\Projects\DemoProject" -release "cits" -testset "BasicWebFlow_Default""
            }
        }	
        stage("Stop Grid"){
	    steps{
		bat "docker-compose down"
            }
        }
    }    
}