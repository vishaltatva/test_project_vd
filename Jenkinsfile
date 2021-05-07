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

    } catch (err) {
        currentBuild.result = 'FAILURE'
        throw err
    }
}
