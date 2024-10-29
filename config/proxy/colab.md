**谷歌colab【[点击直达](https://colab.research.google.com/)】**  （https://colab.research.google.com/）

**运行时在代码前面加一行 ：**!pip install pyaes

**相关代码【[点击直达](https://raw.githubusercontent.com/zzzhhh1/ssvpn/refs/heads/main/ss12)】**

**nekoray** **软件下载和使用教程【[点击直达](https://kjgx668.blogspot.com/2024/06/2024windowsnekoray-tunsing.html)】**

**代码**：

```
import requests

import base64

import json

import pyaes

import binascii

from datetime import datetime



print("      H͜͡E͜͡L͜͡L͜͡O͜͡ ͜͡W͜͡O͜͡R͜͡L͜͡D͜͡ ͜͡E͜͡X͜͡T͜͡R͜͡A͜͡C͜͡T͜͡ ͜͡S͜͡S͜͡ ͜͡N͜͡O͜͡D͜͡E͜͡")

print("𓆝 𓆟 𓆞 𓆟 𓆝 𓆟 𓆞 𓆟 𓆝 𓆟 𓆞 𓆟")

print("Author : 𝐼𝑢")

print(f"Date   : {datetime.today().strftime('%Y-%m-%d')}")

print("Version: 1.0")

print("𓆝 𓆟 𓆞 𓆟 𓆝 𓆟 𓆞 𓆟 𓆝 𓆟 𓆞 𓆟")

print("𝐼𝑢:")

print(r"""

⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡠⠤⠀⠀⠀⠀⠀⠀⠀

⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡴⠁⠀⡰⠀⠀⠀⠀⠀⠀⠀

⠀⠀⠀⠀⠀⠀⠀⠀⢀⡎⢀⠀⠀⠁⠀⠀⠀⠀⠀⠀⠀

⣀⠀⠀⠀⠀⠀⠀⡠⠬⡡⠬⡋⠀⡄⠀⠀⠀⠀⠀⠀⠀

⡀⠁⠢⡀⠀⠀⢰⠠⢷⠰⠆⡅⠀⡇⠀⠀⠀⣀⠔⠂⡂

⠱⡀⠀⠈⠒⢄⡸⡑⠊⢒⣂⣦⠄⢃⢀⠔⠈⠀⠀⡰⠁

⠀⠱⡀⠀⠀⡰⣁⣼⡿⡿⢿⠃⠠⠚⠁⠀⠀⢀⠜⠀⠀

⠀⠀⠐⢄⠜⠀⠈⠓⠒⠈⠁⠀⠀⠀⠀⠀⡰⠃⠀⠀⠀

⠀⠀⢀⠊⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠾⡀⠀⠀⠀⠀

⠀⠀⢸⣄⠀⠀⡀⠀⠀⠀⠀⠀⠀⠀⠀⣀⡇⠀⠀⠀⠀

⠀⠀⠸⢸⣳⠦⣍⣁⣀⣀⣀⣀⣠⠴⠚⠁⠇⠀⠀⠀⠀

⠀⠀⠀⢳⣿⠄⠸⠢⠍⠉⠉⠀⠀⡠⢒⠎⠀⠀⠀⠀⠀

⠀⠀⠀⠣⣀⠁⠒⡤⠤⢤⠀⠀⠐⠙⡇⠀⠀⠀⠀⠀⠀

⠀⠀⠀⠀⠣⡀⡼⠀⠀⠈⠱⡒⠂⡸⠁⠀⠀⠀⠀⠀⠀

⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠑⢒⠁⠀⠀⠀⠀⠀⠀⠀

""")





a = 'http://api.skrapp.net/api/serverlist'

b = {

    'accept': '/',

    'accept-language': 'zh-Hans-CN;q=1, en-CN;q=0.9',

    'appversion': '1.3.1',

    'user-agent': 'SkrKK/1.3.1 (iPhone; iOS 13.5; Scale/2.00)',

    'content-type': 'application/x-www-form-urlencoded',

    'Cookie': 'PHPSESSID=fnffo1ivhvt0ouo6ebqn86a0d4'

}

c = {'data': '4265a9c353cd8624fd2bc7b5d75d2f18b1b5e66ccd37e2dfa628bcb8f73db2f14ba98bc6a1d8d0d1c7ff1ef0823b11264d0addaba2bd6a30bdefe06f4ba994ed'}

d = b'65151f8d966bf596'

e = b'88ca0f0ea1ecf975'



def f(g, d, e):

    h = pyaes.AESModeOfOperationCBC(d, iv=e)

    i = b''.join(h.decrypt(g[j:j+16]) for j in range(0, len(g), 16))

    return i[:-i[-1]]



j = requests.post(a, headers=b, data=c)



if j.status_code == 200:

    k = j.text.strip()

    l = binascii.unhexlify(k)

    m = f(l, d, e)

    n = json.loads(m)

    for o in n['data']:

        p = f"aes-256-cfb:{o['password']}@{o['ip']}:{o['port']}"

        q = base64.b64encode(p.encode('utf-8')).decode('utf-8')

        r = f"ss://{q}#{o['title']}"

        print(r)


```

