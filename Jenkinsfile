pipeline{
	agent any
	
	tools{
		gradle 'Gradle'
		jdk 'JDK'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch:'main',url:'https://github.com/icemberg/MyGradle.git'
			}
		}
		
		stage('Build'){
			steps{
				sh './gradlew clean build --stacktrace --info'
			}
		}
		
		stage('Test'){
			steps{
				sh './gradlew test'
			}
		}
		
		stage('Run Application'){
			steps{
				sh './gradlew run'
			}
		}
	}
		
	post{
		success{
			echo "Build and deployment successful"
		}
		failure{
			echo "Build failed!"
		}
	}
}

