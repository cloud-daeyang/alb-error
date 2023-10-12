# ALB Error creater

```
pip3 install flask
```

```
from flask import Flask, request

app = Flask(__name__)

@app.route('/<int:status_code>')
def bad_request(status_code):
    return f'{status_code}_error', status_code

app.run(host='0.0.0.0', port=80)
```

```
python3 app.py &
```

# loadbalancer_dns 수정 해야함!!

## 404 에러
```
curl http://{loadbalancer_dns}/404
```

## 503 에러
```
curl http://{loadbalancer_dns}/503
```

## 504 에러
```
curl http://{loadbalancer_dns}/504
```

# Stop the Application
```
pkill -9 python3
```
