

def myTasks = ['hello', 'world']

stage('init') {
  node('ci') {
    checkout scm
    sh 'ls -la'
  }
}

stage('test') {
  tasks = [:]
  for (i = 0; i < myTasks.length; i++) {
    def task = myTasks[i]
    tasks[task] = {
      node('ci') {
        echo tasks
        sh 'ls -la'
      }
    }
  }
  parallel tasks
}
