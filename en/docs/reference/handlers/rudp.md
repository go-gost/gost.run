# UDP远程端口转发

Name: `rudp`

Status： Stable

RUDP处理器根据服务中的转发器配置，将数据转发给指定的目标主机。

=== "CLI"

	```bash
	gost -L rudp://:10053/:53
	```

=== "File (YAML)"

    ```yaml
	services:
	- name: service-0
	  addr: :10053
	  handler:
		type: rudp
	  listener:
		type: rudp
	  forwarder:
	    nodes:
		- name: target-0
		  addr: :53
	```

## 参数列表

无

!!! note "限制"
    rudp处理器只能与[rudp监听器](/reference/listeners/rudp/)一起使用，构建UDP远程端口转发服务。


