#!/usr/bin/env groovy

pipeline
{
    agent none

    options
    {
        buildDiscarder(logRotator(numToKeepStr: '3', artifactNumToKeepStr: '3'))
    }

    stages
    {
        stage('windows')
        {
            agent { label "windows && build && vs2019" }
            environment
            {
                UE4_ROOT = 'C:\\UE_4.26'
            }
            stages
            {
                stage('windows build')
                {
                    steps
                    {
                        // bat """
                        //     call ../setEnv64.bat
                        //     make LibCarla
                        // """
                        // bat """
                        //     call ../setEnv64.bat
                        //     make PythonAPI
                        // """
                        bat """
                            call ../setEnv64.bat
                            make CarlaUE4Editor"
                        """
                        // bat """
                        //     call ../setEnv64.bat
                        //     make plugins
                        // """
                    }
                }
            }
        }
    }
}
