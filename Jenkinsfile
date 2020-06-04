#!/usr/bin/env groovy
import hudson.model.*
import java.net.URL

node{
    // first job to pull / clone the code from the repo
    stage('git checkout'){
        git 'https://github.com/npsoni88/DevOpsClassCodes.git'
    }
    
    // second job to compile the code
    stage('compile'){
        withMaven(maven:'honeywellMaven'){
            sh 'mvn compile'
        }
    }
    
    // package the code
    stage('compile'){
        withMaven(maven:'honeywellMaven'){
            sh 'mvn package'
        }
    }
    
}