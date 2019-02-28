node {
	stage("startup") {
		//Remove later.... sho that Jenkinsfile works
		echo "start build"
		env.PATH = "/usr/local/bin/:${env.PATH}"
		env.TF_LOG = "INFO" //TRACE, DEBUG, INFO, WARN or ERROR 
		env.AWS_DEFAULT_REGION = "eu-west-1"

                //Packer version print
                sh "packer --version"

		//Ansible version print
		sh "ansible --version"
	}
        stage("prepare") {

                //Checkout current project .. other can be checked out using git
                checkout scm
        }
	stage("bake") {
		//Run packer to build RHEL base AMI 
		sh "packer build packerfiles/example_app_ami.json"
	}
}
