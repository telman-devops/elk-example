##### build node js app
    docker build -t demo-app .

##### prepare for registry
    docker tag node-app:latest 870414/demo-app:node-1.0

##### push into private registry
    docker push 870414/demo-app:node-1.0