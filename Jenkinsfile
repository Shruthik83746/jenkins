pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Generate HTML Report') {
            steps {
                script {
                    def htmlContent = """
                   <html>
	<head>
	<title>User Registration Form</title>
	</head>
	<body>
		<h1>Registration form</h1>
		<form action="registration.html"method="post">
			<img src="vbit-logo.png"><br/>
			Firstname<br>
			<input type="text"name="fname"><br/>
			Lastname<br>
			<input type="text"name="lname"><br/>
			Email<br>
			<input type="text"name="email"><br/>
			Age<br>
			<input type="number"name="age"><br/>
			Phone number<br>
			<input type="digit"name="phnumber"><br/>
			Gender<br>
			male
			<input type="radio"name="gender" value="male">
			female
			<input type="radio"name="gender" value="female">
			others
			<input type="radio"name="gender" value="others">
			<br/>
			<input type="submit"value="Register"><br/>
		</form>
	</body>
</html>

                    """

                    writeFile file: 'report.html', text: htmlContent
                    archiveArtifacts artifacts: 'report.html'
                }
            }
        }
    }
}
