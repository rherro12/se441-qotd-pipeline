stage "DEV-QA"

node { 
	git url: 'https://github.com/rherro12/se441-qotd.git'
	
	def gradleHome = tool 'Gradle 2.13'
	bat "${gradleHome}\\bin\\gradle.bat assemble uploadArchives test sonarqube"
	
	step([$class: 'ArtifactArchiver', artifacts: '**/*.war', fingerprint: true])
}