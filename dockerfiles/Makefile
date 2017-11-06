SRC?=$(shell dirname `pwd`)
build: 
	docker build -t tf_course . 

bash: build
	docker run -it -v $(SRC):/app tf_course bash

jupyter: build
	docker run -it -v $(SRC):/app -p 8899:8899 tf_course
