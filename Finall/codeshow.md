# api智能价值代码示例
#### 通用票据识别  
**输入代码**
```
f = open('piaoju1.jpg', 'rb')
img = base64.b64encode(f.read())


access_token = '24.c903185daa3cb923b7f89f9c9d175cf8.2592000.1595261057.282335-20509503'
def wenzi(image)->dict:
    url = 'https://aip.baidubce.com/rest/2.0/ocr/v1/receipt'+ "?access_token=" + access_token
    header = {
        'Content-Type':'application/x-www-form-urlencoded',
    }
    params = {
        "image":img
    }
    response = requests.post(request_url, data=params, headers=headers)
    data = response.json()
    return data
票据 = wenzi('piaoju')
票据
```
**返回结果**
```
{'log_id': 4651028328460549493,
 'words_result_num': 22,
 'words_result': [{'location': {'width': 98,
    'top': 38,
    'left': 59,
    'height': 114},
   'words': 'R'},
  {'location': {'width': 953, 'top': 209, 'left': 55, 'height': 67},
   'words': '1【省基】迪巧(维D钙咀嚼60片/瓶'},
  {'location': {'width': 81, 'top': 220, 'left': 1192, 'height': 54},
   'words': '2瓶'},
  {'location': {'width': 507, 'top': 227, 'left': 1522, 'height': 67},
   'words': '用法:一日2次口服'},
  {'location': {'width': 291, 'top': 279, 'left': 127, 'height': 52},
   'words': '片(听似))'},
  {'location': {'width': 531, 'top': 316, 'left': 1522, 'height': 65},
   'words': '如不能吞服,请研碎!'},
  {'location': {'width': 492, 'top': 369, 'left': 581, 'height': 66},
   'words': '剂量:每次1片(1片)'},
  {'location': {'width': 318, 'top': 506, 'left': 86, 'height': 61},
   'words': '2杞枣口服液'},
  {'location': {'width': 456, 'top': 515, 'left': 822, 'height': 57},
   'words': '10ml*10支/盒6盒'},
  {'location': {'width': 492, 'top': 522, 'left': 1522, 'height': 70},
   'words': '用法:一日2次口服'},
  {'location': {'width': 493, 'top': 661, 'left': 586, 'height': 70},
   'words': '剂量:每次10ml(1支)'},
  {'location': {'width': 298, 'top': 800, 'left': 982, 'height': 59},
   'words': '以下为空白'},
  {'location': {'width': 595, 'top': 1796, 'left': 31, 'height': 116},
   'words': '医师签名:李秀珍'},
  {'location': {'width': 236, 'top': 1835, 'left': 1736, 'height': 74},
   'words': '收费员:'},
  {'location': {'width': 944, 'top': 1940, 'left': 40, 'height': 90},
   'words': '亥处方已通过广东省数字证书认证中心认证'},
  {'location': {'width': 100, 'top': 2055, 'left': 145, 'height': 51},
   'words': '审核'},
  {'location': {'width': 111, 'top': 2063, 'left': 507, 'height': 59},
   'words': '调剂'},
  {'location': {'width': 98, 'top': 2062, 'left': 880, 'height': 49},
   'words': '核对'},
  {'location': {'width': 105, 'top': 2058, 'left': 1240, 'height': 58},
   'words': '发药'},
  {'location': {'width': 417, 'top': 2044, 'left': 1527, 'height': 66},
   'words': '药费:252.18'},
  {'location': {'width': 352, 'top': 2114, 'left': 1527, 'height': 66},
   'words': '材料费:0.00'},
  {'location': {'width': 473, 'top': 2207, 'left': 1565, 'height': 70},
   'words': 'b古口右加'}]}
   ```
