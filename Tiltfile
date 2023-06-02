# Build
custom_build(
    # Name of the container image
    ref = 'config-server',
    # Command to build the container image
    command = 'mvnw spring-boot:build-image -D skipTests -D spring-boot.build-image.imageName=%EXPECTED_REF%',
    # Files to watch that trigger a new build
    deps = ['pom.xml', 'src']
)

# Deploy
k8s_yaml(['deploy/k8s/deployment.yml', 'deploy/k8s/service.yml'])

# Manage
k8s_resource('config-server', port_forwards=['8888'])