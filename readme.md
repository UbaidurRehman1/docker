<h2>Docker</h2>

<ol>
    <h3>Docker Important commands</h3>
    <li>for all docker containers <strong>docker ps -a</strong></li>
    <li>for all running docker containers <strong>docker ps</strong></li>
    <li>to run docker container <strong>docker run image_name</strong></li>
    <li>to run docker container in deamon <strong>docker run -d image_name</strong></li>
    <li>to map port use <strong>docker -p port:port</strong></li>
    <li>to check logs <strong>docker logs -f container_id</strong></li>
    <li>to add environment: use -e var:var-name</li>
    <li>To include volume: (mongo db)</li>
    <ol>
        <li>add -v and /to/path/:data/db</li>
    </ol>
    <ol>
        <h3>House Keeping</h3>
        <li>Kill all running containers: docker kill $(docker ps -q)</li>
        <li>Delete all stopped containers: docker rm $(docker ps -a -q)</li>
        <li>Remove a docker image: docker rmi image-name</li>
        <li>Delete untagged images: docker rmi $(docker images -q -f dangling=true)</li>
        <li>Delete all images: docker rmi $(docker images -q)</li>
        <li>docker volume rm $(docker volume ls -f dangling=true -q)</li>
    </ol>
    <ol>
        <h3>Logs</h3>
        <li>Check the logs of container: docker logs container_name</li>
        <li>Tail the logs of container: docker logs -f container_name</li>
    </ol>
    <ol>
        <h3>Execute the shell of the container:</h3>
        <li>docker exec -it container-name bash</li>
    </ol>
    <ol>
        <h3>Building Image from docker file: </h3>
        <li>docker build -t tag-name</li>
    </ol>
</ol>

<h5>
    <ol>
        <li>Use relative path in windows</li>
    </ol>
</h5>