pipeline {
    agent any 
    stages {
          stage('one') {
                   steps { 
                           echo 'Hi, this is masho from ubuntu'
                        }
             }
           stage('Two') {
                    steps {
                            input ('Do you want to proceed?')
                          }
               }  
            stage('Three') {
                     when { 
                          not {
                                 branch "master"
                              }
                     }
                     steps {
                             echo "Hello"
                            }  
                        }    
            stage('Four')  {
                            parallel { 
                                stage('unit Test')  { 
                                                    steps {
                                                       echo " Running the unit test .."
                                                     }
                                      }
                                  stage('Integration test')   {
                                                        agent {
                                                               docker {
                                                                        reuseNode false
                                                                        image 'ubuntu'
                                                                }
                                                           }
                                                           step { 
                                                                 echo 'Running the integration test ....'
                                                            }     
                                              }
                                              }
        }                         
        }
        }
        }
