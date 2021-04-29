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

        // Setup tools here
        stage 'Tool Setup'
			sh "${phpBin} -v"
			// Composer deps like deployer
			sh "composer.phar install"
			// Phing
			if (!fileExists('phing-latest.phar')) {
				sh "curl -sS -O https://www.phing.info/get/phing-latest.phar -o ${phingBin}"
			}
			sh "${phingCall} -v"
			sh "printenv"

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
