ARG jdktag=oracle-8-jdk
FROM razikus/armjdk:${jdktag}
RUN apt update && apt install -y curl && rm -rf /var/lib/apt/lists/*
ARG JENKINS_VERSION=2.150.3
ARG JENKINS_URL=https://repo.jenkins-ci.org/public/org/jenkins-ci/main/jenkins-war/${JENKINS_VERSION}/jenkins-war-${JENKINS_VERSION}.war

RUN curl ${JENKINS_URL} -o jenkins.war
RUN mkdir -p /root/.jenkins/
COPY hudson.model.UpdateCenter.xml /root/.jenkins/
ENTRYPOINT ["java", "-jar", "jenkins.war"]
