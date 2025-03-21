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
                    <!DOCTYPE html>
                    <html>
                    <head>
                        <title>Jenkins Pipeline Report</title>
                        <style>
                            body { font-family: Arial, sans-serif; margin: 40px; }
                            h1 { color: #4CAF50; }
                            table { border-collapse: collapse; width: 100%; margin-top: 20px; }
                            th, td { padding: 10px; text-align: left; border-bottom: 1px solid #ddd; }
                            th { background-color: #f2f2f2; }
                        </style>
                    </head>
                    <body>
                        <h1>Pipeline Execution Report</h1>
                        <table>
                            <tr>
                                <th>Stage</th>
                                <th>Status</th>
                            </tr>
                            <tr>
                                <td>Build</td>
                                <td>Success</td>
                            </tr>
                            <tr>
                                <td>Test</td>
                                <td>Success</td>
                            </tr>
                        </table>
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
