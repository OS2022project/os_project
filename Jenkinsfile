node {
	def app
	stage('Clone repository'){
		git 'https://github.com/Juyeon823/os_project-1.git'
	}
	stage('Build image'){
		app = docker.build("juyeon0823/prbasedosp")
	}
	stage('Push image'){
		docker.withRegistry('https://registry.hub.docker.com', 'juyeon'){
			app.push("${env.BUILD_NUMBER}")
			app.push("latest")
		}
	}
}
