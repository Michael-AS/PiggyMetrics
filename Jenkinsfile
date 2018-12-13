node {

    stage("Setup") {
        deleteDir()
    }

    stage("Clone") {
        checkout scm
    }

    stage("Test") {
        sh "mvn test"
    }

    stage("Build") {
        sh "mvn install -DskipTests"
    }

    stage("Package") {

        def accountServiceImage = docker.build("michaelas/piggymetrics-account-service:${env.BUILD_ID}", "./account-service/Dockerfile")
        def authServiceImage = docker.build("michaelas/piggymetrics-auth-service:${env.BUILD_ID}", "./auth-service/Dockerfile")
        def configImage = docker.build("michaelas/piggymetrics-piggymetrics-config:${env.BUILD_ID}", "./config/Dockerfile")
        def gatewayImage = docker.build("michaelas/piggymetrics-gateway:${env.BUILD_ID}", "./gateway/Dockerfile")
        def mongoDbImage = docker.build("michaelas/piggymetrics-mongodb:${env.BUILD_ID}", "./mongodb/Dockerfile")
        def monitoringImage = docker.build("michaelas/piggymetrics-monitoring:${env.BUILD_ID}", "./monitoring/Dockerfile")
        def notificationServiceImage = docker.build("michaelas/piggymetrics-notification-service:${env.BUILD_ID}", "./notification-service/Dockerfile")
        def registryImage = docker.build("michaelas/piggymetrics-registry:${env.BUILD_ID}", "./registry/Dockerfile")
        def statisticsServiceImage = docker.build("michaelas/piggymetrics-statistics-service:${env.BUILD_ID}", "./statistics-service/Dockerfile")
        def turbineStreamServiceImage = docker.build("michaelas/piggymetrics-turbine-stream-service:${env.BUILD_ID}", "./turbine-stream-service/Dockerfile")

    }

    stage("Publish") {

        accountServiceImage.push()
        accountServiceImage.push("latest")

        authServiceImage.push()
        authServiceImage.push("latest")

        configImage.push()
        configImage.push("latest")

        gatewayImage.push()
        gatewayImage.push("latest")

        authServiceImage.push()
        authServiceImage.push("latest")

        mongoDbImage.push()
        mongoDbImage.push("latest")

        monitoringImage.push()
        monitoringImage.push("latest")

        notificationServiceImage.push()
        notificationServiceImage.push("latest")

        registryImage.push()
        registryImage.push("latest")

        statisticsServiceImage.push()
        statisticsServiceImage.push("latest")

        turbineStreamServiceImage.push()
        turbineStreamServiceImage.push("latest")

    }

}