@Library('Jenkins-Shared-Library-03') _

def config = [
    // Project Variables
    PROJECT_NAME: "boardgame",  // required     
    PROJECT_KEY: "boardgame",   // required
    COMPONENT: "backend",   // required

    // Git Variables
    MY_GIT_URL: "https://github.com/vaheedgithubac/Boardgame.git", // required
    MY_GIT_REPO_TYPE: "public",   // required (public/private)
    MY_GIT_CREDENTIALS_ID: "",    // required for private repos
    MY_GIT_BRANCH: "",            // Defaults to "main" if not set

    // JACOCO Variables
    EXECUTE_JACOCO_STAGE: "yes",                   // required (yes/no)
    JACOCO_GROUPID: "org.jacoco",                 // required
    JACOCO_ARTIFACT_ID: "jacoco-maven-plugin",    // required
    JACOCO_VERSION: "0.8.7",                      // required
    JACOCO_GOAL: "prepare-agent",                 // required

    // SONARQUBE SCAN Variables
    EXECUTE_SONARSCAN_STAGE: "no",        // required (yes/no)
    SONARQUBEAPI: "sonarqube-server",     // required 
    SONAR_INSTALL_NAME: "sonarscanner",   // required
    TIMEOUT_MINUTES: 5,                   // For Sonarqube Quality gate (Default is 5 Minutes)

    // SONAR QG Variables
    EXECUTE_SONAR_QG_STAGE: "no",   // required (yes/no)

    // TRIVY FS SCAN Variables
    EXECUTE_TRIVY_FS_STAGE: "yes",            // required (yes/no)
    TRIVY_FS_TARGET: ".",                     // Defaults to "." (Current File System)
    TRIVY_FS_SCAN_FORMAT: "table",            // required
    TRIVY_FS_OUTPUT_FORMAT: "txt",            // required 

    // MAVEN Variables
    EXECUTE_MAVEN_STAGE: "yes",      // required (yes/no)
    MAVEN_SKIP_TESTS: true,         // Defaults to 'true'
    MAVEN_GOALS: "clean package",   // Defaults to 'clean package'

    // DOCKER BUILD Variables
    EXECUTE_DOCKER_IMAGE_BUILD_STAGE: "yes",   // required (yes/no)

    // TRIVY IMAGE SCAN Variables
    EXECUTE_TRIVY_IMAGE_STAGE: "yes",            // required (yes/no)
    TRIVY_IMAGE_SCAN_FORMAT: "table",           // required
    TRIVY_IMAGE_OUTPUT_FORMAT: "txt",           // required 

    // DOCKER HUB Registry Variables
    EXECUTE_DOCKER_HUB_PUSH_STAGE: "yes",              // required (yes/no)
    DOCKER_REPO_URI: "docker.io",                     // Defaults to 'docker.io'
    DOCKER_HUB_CREDENTIALS_ID: "docker-prod-creds",   // required 

    // ECR Variables
    EXECUTE_ECR_PUSH_STAGE: "no",           // required (yes/no)
    AWS_ACCOUNT_ID: "",                     // required 
    REGION: "ap-south-1",                   // Defaults to 'ap-south-1' 
    AWS_CREDENTIALS_ID: "aws-prod-creds",   // required 

    // Nexus Variables
    EXECUTE_NEXUS_STAGE: "no",              // required (yes/no)
    NEXUS_HOST: '13.235.95.123',            // required 
    NEXUS_PORT: '8081',                     // required
    NEXUS_PROTOCOL: 'http',                 // required
    NEXUS_VERSION: 'nexus3',                // required
    NEXUS_BASE_REPO: 'vprofile',            // required
    NEXUS_GRP_ID: 'QA',                     // required
    NEXUS_CREDENTIALS_ID: '',               // required

    // EMAIL Variables
    EXECUTE_EMAIL_STAGE: "no",      // required (yes/no)
    FROM_MAIL: "",                  // required
    TO_MAIL: "",                    // required
    REPLY_TO_MAIL: "",              // required
    CC_MAIL: "",                    // Defaults to null
    BCC_MAIL: "",                   // Defaults to null
    ATTACHMENTS: ""                 // Defaults to null  // "trivy-reports/*, owasp-reports/*, surefire-reports/*.xml"
]

// Compute derived Nexus repos
config.NEXUS_SNAP_REPO    = "${config.NEXUS_BASE_REPO}-SNAPSHOT"
config.NEXUS_RELEASE_REPO = "${config.NEXUS_BASE_REPO}-RELEASE"
config.NEXUS_GRP_REPO     = "${config.NEXUS_BASE_REPO}-maven-group"

// Compute ECR repo
config.ECR_REPO_URI = "${config.AWS_ACCOUNT_ID}.dkr.ecr.${config.REGION}.amazonaws.com"

// Call pipeline
PIPELINE_JAVA(config)


// printVars(configMap)
//PIPELINE_JAVA_01(config)
