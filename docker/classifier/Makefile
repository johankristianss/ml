BUILD_IMAGE ?= johan/classifier
PUSH_IMAGE ?= johan/classifier

build:
	docker build -t $(BUILD_IMAGE) . --no-cache
	#docker build -t $(BUILD_IMAGE) . 
push:
	docker tag $(BUILD_IMAGE) $(PUSH_IMAGE) 
	docker push $(PUSH_IMAGE)
shell:
	docker tag $(BUILD_IMAGE) $(PUSH_IMAGE) 
	docker run -v $(HOME):/root/home --gpus all -it -p 18888:8888 $(PUSH_IMAGE) fish
