#<center>DOCKER (Phần 1) </center>

#### 1. Docker là gì? 
* Là một developer, dù là newbie thì chắc hẳn chúng ta đã ít nhất một lần 
nghe tới Docker. Vậy thì Docker là gì, chúng ta sẽ cùng tìm hiểu về nó trong bài viết hôm nay.
* Có rất nhiều cách để định nghĩa về Docker, nhưng mình sẽ hiểu đơn giản như sau:
 Docker là một nền tảng cho cho việc phát triển những dự án của chúng trên một môi trường ảo, tuy ảo nhưng lại thật. 
 Ví dụ khi chúng ta join vào một dự án, đầu tiên chúng ta sẽ phải cài đủ thể loại môi trường như: ruby, rails, rbenv,
  mysql, nginx, phpmyadmin... vân vân và mây mây, điều này thực sự quá mất thời gian và còn chưa kể tới việc xung đột 
  với các thứ mà đã cài trên máy. Từ đó, Docker đã ra đời để giải quyết tất cả vấn đề trên, tất cả sẽ được gói gọn 
  với một vài dòng lệnh cùng với một vài file config. <br>
* Có một slogan cực kỳ nổi tiếng về Docker đó là: "Build once, run anywhere", có thể hiểu là chỉ cần tạo 
Docker Container một lần, và nó có thể chạy trên mọi môi trường (Ubuntu, Mac OS, Window...)

#### 2. Một số khái niệm phổ biến 
* Gồm 4 khái niệm sau: `Image, Container, Docker Engine, Docker Hub`

* Chi tiết hơn: <br>
`IMAGES`: Image giống như những file `.iso`, `.gho` mà các anh chàng IT hay dùng để cài Win hay Ghost cho 
các chị em mỗi khi được nhờ ^_^. Trong Docker, thì `image` là các `image ubuntu, mysql, ruby, php...`
hoặc có thể là image chứa cả `ubuntu, mysql, ruby, php`. Chúng ta hoàn toàn có thể tự build riêng cho mình 
những image. Và từ các image này chúng ta sẽ tạo ra `Container`.<br><br>
`CONTAINER`: là một máy ảo được cấu thành từ các images và sẽ là nơi lưu trữ các tài nguyên của chúng ta. 
Nó sẽ dùng chung tài nguyên của hệ thống với máy host của chúng ta (RAM, CPU, DISK...). Vì thế mà container
chạy rất nhẹ và nhanh, không giống như các môi trường ảo khác như `Vagrant, Homestead`. Hay theo dân dev
chúng ta hay hiểu `image` là một class, còn container là một thể hiện của class đó ^_^ <br><br>
`DOCKER ENGINES`: Giúp chúng ta quản lý việc tạo image, container. Nếu image chưa có trên máy chúng ta thì 
sẽ tiến hành tải vể, có rồi thì "nhét" vào container, hay việc sửa, xóa images và container ... <br><br>
`DOCKER HUB`: Giống như Github, Gitlab..., Docker Hub là nơi lưu trữ, chia sẻ các images mà chúng ta tạo ra.

#### 3. Hướng dẫn cài Docker 
* Cài Docker:
```
sudo apt-get update
sudo apt-get install curl apt-transport-https ca-certificates software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
sudo apt-get install docker-ce

===> Check docker version and status:
docker -v
sudo systemctl status docker
```
* Tới đây, việc cài đặt đã hoàn tất, chúng ta sẽ test xem Docker đã chạy "ngon" chưa 
```
sudo docker run hello-world 

===> Nếu hiển thị như bên dưới tức là nó đã chạy ok rồi đó 

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

```

##### Tới đây thì mình đã hướng dẫn mọi người hiểu Docker là gì, trong phần 2 thì mình sẽ nói về các câu lệnh hay sử dụng và `Docker Compose`
##### Do cũng mới tìm hiểu về Docker nên có thể một số chỗ mình nói sẽ không chính xác hoàn toàn, mong ae gạch đá nhẹ tay.
### Thanks for reading !!!