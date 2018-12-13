node {

    stage("Setup") {
 //       deleteDir()
    }

    stage("Clone") {
   //     checkout scm
    }
/*
    stage("Build") {
        sh "mvn install -DskipTests"
    }

    stage("Test") {
        sh "mvn test"
    }
*/
    stage("Package") {

        def accountServiceImage = docker.build("michaelas/piggymetrics-account-service:${env.BUILD_ID}", "./account-service/")
        def authServiceImage = docker.build("michaelas/piggymetrics-auth-service:${env.BUILD_ID}", "./auth-service/")
        def configImage = docker.build("michaelas/piggymetrics-piggymetrics-config:${env.BUILD_ID}", "./config/")
        def gatewayImage = docker.build("michaelas/piggymetrics-gateway:${env.BUILD_ID}", "./gateway/")
        def mongoDbImage = docker.build("michaelas/piggymetrics-mongodb:${env.BUILD_ID}", "./mongodb/")
        def monitoringImage = docker.build("michaelas/piggymetrics-monitoring:${env.BUILD_ID}", "./monitoring/")
        def notificationServiceImage = docker.build("michaelas/piggymetrics-notification-service:${env.BUILD_ID}", "./notification-service/")
        def registryImage = docker.build("michaelas/piggymetrics-registry:${env.BUILD_ID}", "./registry/")
        def statisticsServiceImage = docker.build("michaelas/piggymetrics-statistics-service:${env.BUILD_ID}", "./statistics-service/")
        def turbineStreamServiceImage = docker.build("michaelas/piggymetrics-turbine-stream-service:${env.BUILD_ID}", "./turbine-stream-service/")

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