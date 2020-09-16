VERSION = 0.0.1

build:
	docker build . --no-cache --tag dia:${VERSION}

run:
	docker run --rm \
    -v /etc/localtime:/etc/localtime:ro \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -v "${HOME}"/Downloads:/root/Downloads \
    -v "${HOME}"/Documents:/root/Documents \
    -v "${HOME}"/.config/dia:/root/.dia \
		-v "${HOME}"/devel:/root/devel \
    -e DISPLAY="unix${DISPLAY}" \
		--net=host \
    --name dia \
    dia:0.0.1

# Post https://habr.com/ru/post/240509/
xsecurity:
	xhost +si:localuser:root
