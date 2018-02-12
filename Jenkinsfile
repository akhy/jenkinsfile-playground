

stage('init') {
  node('ci') {
    checkout scm
    sh 'ls -la'
  }
}

stage('test') {
  myTasks = ['hello', 'world']
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
