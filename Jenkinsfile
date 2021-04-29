node {
    // ENV variables
    env.PWD = pwd()
    env.STAGE = STAGE
    env.TAG = TAG
    env.REINSTALL_PROJECT = REINSTALL_PROJECT
    env.DELETE_VENDOR = DELETE_VENDOR
    env.GENERATE_ASSETS = GENERATE_ASSETS
    env.DEPLOY = DEPLOY

    try {
        // Update Deployment
        checkout scm

        stage 'Tool Setup'
        // Setup tools here

        stage 'Magento Setup'
        // Setup and update Magento
        
        stage 'Asset Generation'
        if (GENERATE_ASSETS == 'true') {
            // Generate and package assets
        }

        stage 'Deployment'
        if (DEPLOY == 'true') {
            // Trigger deployment and start release
        }

    } catch (err) {
        currentBuild.result = 'FAILURE'
        throw err
    }
}
