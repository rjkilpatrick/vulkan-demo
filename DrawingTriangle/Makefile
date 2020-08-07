VULKAN_SDK_PATH = /usr/local/vulkan-sdk/1.2.148.0/x86_64

CFLAGS = -std=c++17 -I$(VULKAN_SDK_PATH)/include
LDFLAGS = -L$(VULKAN_SDK_PATH)/lib `pkg-config --static --libs glfw3` -lvulkan

DrawingTriangle: main.cpp
	g++ $(CFLAGS) -o DrawingTriangle main.cpp $(LDFLAGS)

.PHONY: test clean

test: DrawingTriangle
	LD_LIBRARY_PATH=$(VULKAN_SDK_PATH)/lib VK_LAYER_PATH=$(VULKAN_SDK_PATH)/etc/vulkan/explicit_layer.d ./DrawingTriangle

clean:
	rm -f DrawingTriangle