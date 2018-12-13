node {

    stage("Setup") {
        deleteDir()
    }

    stage("Clone") {
        checkout scm
    }

    stage("Build") {
        sh "mvn install -DskipTests"
    }

    stage("Test") {
        sh "mvn test"
    }

    stage("Build & Publish") {

        def accountServiceImage = docker.build("michaelas/piggymetrics-account-service:${env.BUILD_ID}", "./account-service/")
        accountServiceImage.push()
        accountServiceImage.push("latest")

        def authServiceImage = docker.build("michaelas/piggymetrics-auth-service:${env.BUILD_ID}", "./auth-service/")
        authServiceImage.push()
        authServiceImage.push("latest")

        def configImage = docker.build("michaelas/piggymetrics-piggymetrics-config:${env.BUILD_ID}", "./config/")
        configImage.push()
        configImage.push("latest")

        def gatewayImage = docker.build("michaelas/piggymetrics-gateway:${env.BUILD_ID}", "./gateway/")
        gatewayImage.push()
        gatewayImage.push("latest")

        def mongoDbImage = docker.build("michaelas/piggymetrics-mongodb:${env.BUILD_ID}", "./mongodb/")
        mongoDbImage.push()
        mongoDbImage.push("latest")

        def monitoringImage = docker.build("michaelas/piggymetrics-monitoring:${env.BUILD_ID}", "./monitoring/")
        monitoringImage.push()
        monitoringImage.push("latest")

        def notificationServiceImage = docker.build("michaelas/piggymetrics-notification-service:${env.BUILD_ID}", "./notification-service/")
        notificationServiceImage.push()
        notificationServiceImage.push("latest")

        def registryImage = docker.build("michaelas/piggymetrics-registry:${env.BUILD_ID}", "./registry/")
        registryImage.push()
        registryImage.push("latest")

        def statisticsServiceImage = docker.build("michaelas/piggymetrics-statistics-service:${env.BUILD_ID}", "./statistics-service/")
        statisticsServiceImage.push()
        statisticsServiceImage.push("latest")

        def turbineStreamServiceImage = docker.build("michaelas/piggymetrics-turbine-stream-service:${env.BUILD_ID}", "./turbine-stream-service/")
        turbineStreamServiceImage.push()
        turbineStreamServiceImage.push("latest")

    }

    stage("Deploy") {
        
    }

}







