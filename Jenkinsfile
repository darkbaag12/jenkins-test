pipeline {
	agent any
	stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // 실제 빌드 명령어 (예: sh 'mvn clean package' 또는 bat 'gradlew build' 등)
            }
        }
    }
	
	post {
        success {
            echo 'Build Succeeded! Saving result to txt file...'
            // build-result.txt 파일 생성 및 내용 기록
            writeFile file: 'build-result.txt', text: 'Build Succeeded! Date: ' + new Date().toString()
            // 젠킨스 결과 화면에 txt 파일을 다운로드할 수 있게 박제(아카이빙)
            archiveArtifacts artifacts: 'build-result.txt', onlyIfSuccessful: true
        }
    }
}
	
	
	
	
}