@Library('Jenkins-Shared-Library-03') _

def configMap = [
                       // Project Variables //
    PROJECT_NAME: "myapp",                    // required
    PROJECT_KEY: "myapp",                    // required
    COMPONENT: "backend",                  // required

                       // Git Variables //
     MY_GIT_URL: "https://github.com/vaheedgithubac/Boardgame.git",
     MY_GIT_REPO_TYPE: "public",                   // required (public or private)
     MY_GIT_CREDENTIALS_ID: "",                         // required for private repos
     MY_GIT_BRANCH: "",                         // Defaults to "main" if not set
     //MY_GIT_LATEST_COMMIT_ID: get_latest_short_commit(),  // <-- calls call() from shared library

                       // JACOCO Variables //
    EXECUTE_JACOCO_STAGE: "no",                       // required (yes/no)
    JACOCO_GROUPID: "org.jacoco",               // required
    JACOCO_ARTIFACT_ID: "jacoco-maven-plugin",      // required
    JACOCO_VERSION: "0.8.7",                    // required
    JACOCO_GOAL: "prepare-agent",            // required

                      // SONARQUBE SCAN Variables //
    EXECUTE_SONARSCAN_STAGE: "no",                       // required (yes/no)
    SONARQUBEAPI: "sonarqube-server",         // required
    // SCANNER_HOME: "${tool 'sonarscanner'}",   // required
    TIMEOUT_MINUTES: 5,                          // For Sonarqube Quality gate (Default is 5 Minutes)

                      // SONAR QG Variables //
    EXECUTE_SONAR_QG_STAGE: "no",                       // required (yes/no)

                       // MAVEN Variables //
    EXECUTE_MAVEN_STAGE: "no",                       // required (yes/no)
    MAVEN_SKIP_TESTS: true,                       // Defaults to 'true'
    MAVEN_GOALS: "clean package",            // Defaults to 'clean package' 
                      
                       // TRIVY FS SCAN Variables //
    EXECUTE_TRIVY_FS_STAGE: "no",                 // required (yes/no)
    FS_TARGET: "." ,                 // Defaults to "." (Current File System)
    TRIVY_FILE_SYSTEM_REPORT_FORMAT: "html",               // required

                       // DOCKER BUILD Variables //
    EXECUTE_DOCKER_IMAGE_BUILD_STAGE: "no",

                       // TRIVY IMAGE SCAN Variables //
    EXECUTE_TRIVY_IMAGE_STAGE: "no",                 // required (yes/no)
    IMAGE_TARGET: "image",              // Defaults to "." (Current File System)
    TRIVY_IMAGE_REPORT_FORMAT: "html",               // required
    
                       // DOCKER HUB Registry Variables //
    EXECUTE_DOCKER_HUB_PUSH_STAGE: "no",                 // required (yes/no)
    DOCKER_REPO_URI: "docker.io",          // Defaults to 'docker.io'
    DOCKER_HUB_CREDENTIALS_ID: "docker-prod-creds",  // required

                       // ECR Variables //
    EXECUTE_ECR_PUSH_STAGE: "no",                       // required (yes/no)
    AWS_ACCOUNT_ID: "",                         // required
    REGION: "ap-south-1" ,              // Defaults to 'ap-south-1'
    ECR_REPO_URI: "${AWS_ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com",
    AWS_CREDENTIALS_ID: "aws-prod-creds",

                       // Nexus Variables //
    EXECUTE_NEXUS_STAGE: "no",                               // required (yes/no)
    NEXUS_HOST: '13.235.95.123',                    // required
    NEXUS_PORT: '8081',                             // required
    NEXUS_PROTOCOL: 'http',                             // required
    NEXUS_VERSION: 'nexus3',                           // required

    NEXUS_BASE_REPO: 'vprofile',                         // required
    NEXUS_SNAP_REPO: "${NEXUS_BASE_REPO}-SNAPSHOT",      // required
    NEXUS_RELEASE_REPO: "${NEXUS_BASE_REPO}-RELEASE",       // required
    NEXUS_GRP_REPO: "${NEXUS_BASE_REPO}-maven-group",   // required

    NEXUS_GRP_ID: 'QA',                               // required
    NEXUS_CREDENTIALS_ID: 'nexus-creds',                      // required
    // NEXUS_CREDENTIALS: credentials('nexus-creds'),         // required
    // NEXUS_ARTIFACT_VERSION: "${BUILD_ID}-${BUILD_TIMESTAMP}",  // Requires "Build Timestamp" plugin

                       // EMAIL Variables //
    EXECUTE_EMAIL_STAGE: "no",                               // required (yes/no)
    FROM_MAIL: "",                                 // required
    TO_MAIL: "",                                 // required
    REPLY_TO_MAIL: "",                                 // required
    CC_MAIL: "",                                 // Defaults to null
    BCC_MAIL: "",                                 // Defaults to null
    ATTACHMENTS: ""                                  // Defaults to null  // "trivy-reports/*, owasp-reports/*, surefire-reports/*.xml"               
]
// printVars(configMap)
PIPELINE_JAVA_01(configMap)
// pipelineJava(configMap)
