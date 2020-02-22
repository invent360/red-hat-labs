node("maven") {
            sh "git clone https://github.com/openshift/openshift-jee-sample.git ."
            sh "mvn -B -Popenshift package"
          }
node("jenkins-slave-ansible") {
            sh "ansible --version"
          }
node("jenkins-slave-python") {
            sh "python --version"
          }
 node("jenkins-slave-golang") {
            sh "go --version"
          }
node("jenkins-slave-gradle") {
            sh "gradle --version"
          }