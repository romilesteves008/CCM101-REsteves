# Mission Reflection

Writing a docker-compose.yml file makes a cloud engineer's job much easier because the whole setup lives in one file instead of in long commands that I have to remember and retype. I can start two containers with a single command, repeat the same deployment anytime, and share the file with a teammate so they get the exact same result. It also removes a lot of typing mistakes, and I can track changes to the file in GitHub.

If you make an indentation error in YAML, such as using a Tab instead of spaces, Docker Compose cannot read the file and shows a syntax error, so nothing gets deployed. YAML depends on spaces to understand which settings belong to which service, so even one misplaced space can break the structure. This taught me to be very careful when pasting code into nano.

We used environment variables like MYSQL_PASSWORD so the containers can be configured without changing the image itself. The database and the Nextcloud container both need the same credentials, so setting them as variables lets them connect to each other. It also makes the file easier to change, and in a real project the passwords would be kept in a separate secure file instead of being written directly in the code.

Deploying a working enterprise cloud storage system in just a few minutes felt amazing and a little unbelievable. I only wrote a short file and ran one command, and then I saw the Nextcloud setup page in my browser. It made me realize how powerful containers and automation are, and it made the work feel real instead of just theory.

Since Mission 1, my understanding of cloud computing has changed a lot. At first I thought it was only about storing files online. Now I understand it is about building, deploying, and managing services with tools, code, and automation, and that a good cloud engineer writes infrastructure instead of clicking through it.
