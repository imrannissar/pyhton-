
**Response grabber with argument console** 
```py
import requests
import argparse

parser = argparse.ArgumentParser()
parser.add_argument("--url", help="Enter Url")
args = parser.parse_args()
r = requests.get(args.url)
file = open('t.txt',"w+")
file.write(r.text)
file.close()
```

**Command line argument in python**

```py
import argparse


    parser = argparse.ArgumentParser()
    parser.add_argument("--name", help="first number")
    parser.add_argument("--mname ", help="second number")
    parser.add_argument("--gender", help="operation", \
                        choices=["mame","female","other"])

    args = parser.parse_args()

    print(args.name)
    print(args.mname)
    print(args.gender)
    
Syntax
python test.py --name imran --mname nissar --gender male 
In gender their are choices so we cant take any other input
```
**Webhooks with python**

```py
import json
import requests
import time
import argparse
parser = argparse.ArgumentParser()
parser.add_argument("--Target", help="Enter your Target")
args = parser.parse_args()
print (args.Target)
def slack(msg):
    t_data={}
    t_data['text']=msg
    data=json.dumps(t_data)
    res=requests.post("https://hooks.slack.com/services/TEST/TEST",data=data,headers={"content-type":"application/json"})
    print('sending to slack [ Automation ]')
slack('Scannig domain ' + args.Target)
Syntax
Python webhook.py --Target test.com
```

