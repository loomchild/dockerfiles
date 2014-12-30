Repository containing my docker images. 

# Building

Go to 

1. Go to directory with Dockerfile

    cd [project]/[arch]

1. Prepare configuration, remove sample suffix:

    cp ../config/[configfile].sample [configfile]
	
1. Modify configuration if needed (changes won't be committed)

1. Build an image:

    docker build -t [user]/[tag] .

# Running

1. Run an image:

    docker run -d --name [name] -p [port]:[port] --link [othercontainter]:[host] [user]/[tag]
