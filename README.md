# falcon-wsgi-example

学习 Python 的 Web 框架 Falcon

WSGI 协议

## 安装依赖

```
python3 -m pip install -r requirements.txt
```


## WSGI Tutorial

实现了 WSGI Tutorial 的 image-sharing app

提交图片

```shell
http POST localhost:8000/images Content-Type:image/png < /Users/apple/IMG_0976_little.png
```

查询图片

```shell
http GET localhost:8000/images/<image_name.xxx>
```


## 运行测试


### 运行单元测试 

#### 运行所有测试

```shell
coverage run -m pytest tests
```

#### 运行单个测试

```shell
pytest tests -k <test_func_name>
```

### 运行功能测试

#### 启动 app

```shell
LOOK_STORAGE_PATH=./images gunicorn --reload 'app.app:get_app()'
```

#### 运行测试

```shell
pytest tests -k test_posted_image_gets_saved
```
