---
layout: post
lazyimages: "enabled"
title:  "Viết một trợ lý ảo nói Tiếng Việt sử dụng ChatGPT hoặc Bard Google - Python"
author: sal
categories: [ Coding 💻 ]
tags: [ python, lập trình ]
image: assets/images/2023/lap-trinh/avts/tro-ly-ao-chatgpt.webp
# rating: 4.5
isGithubComments: true
permalink: lap-trinh/assistant-chatgpt-vietnamese
excerpt: Chat openai hiện đang là chủ đề hot trên thế giới.
description: Chat openai hiện đang là chủ đề hot trên thế giới.
adsense: "enabled"
keywords:
  - chat openai
  - python cơ bản
  - python3
  - bot gpt
  - emotion recognition
date: 2023-12-01 01:12:10 +0700
---

 **Mục tiêu**

Chatbot dùng micro laptop sẽ nhận thông tin và trả lời câu hỏi của người dùng nói bằng tiếng Việt, sử dụng API chat gpt 3.5 của ChatGPT (account chat gpt free) hoặc Bard Google.

**Yêu cầu**

*   Chatbot phải có thể nhận diện giọng nói của người dùng.
*   Chatbot phải có thể hiểu và trả lời các câu hỏi của người dùng bằng tiếng Việt.
*   Chatbot phải sử dụng API của ChatGPT và Bard Google để trả lời các câu hỏi của người dùng.

**Thiết kế**

Chatbot sẽ được thiết kế theo mô hình sau:

```
Micro laptop
|
|
+-- Nhận dạng giọng nói
|
|
+-- Xử lý ngôn ngữ tự nhiên
|
|
+-- API ChatGPT hoặc API Bard Google
|
|
+-- Trả lời người dùng

```

**Nhận dạng giọng nói**

Nhận dạng giọng nói sẽ được thực hiện bằng cách sử dụng thư viện SpeechRecognition: [https://pypi.org/project/SpeechRecognition/](https://pypi.org/project/SpeechRecognition/) của Python. Thư viện này cung cấp các chức năng để nhận dạng giọng nói của người dùng từ âm thanh đầu vào.

**Xử lý ngôn ngữ tự nhiên**

Xử lý ngôn ngữ tự nhiên sẽ được thực hiện bằng cách sử dụng thư viện NLTK: [https://www.nltk.org/](https://www.nltk.org/) của Python. Thư viện này cung cấp các chức năng để phân tích và hiểu ngôn ngữ tự nhiên.

**API ChatGPT**

API ChatGPT sẽ được sử dụng để trả lời các câu hỏi của người dùng mà có thể trả lời bằng cách tạo văn bản. Ví dụ, nếu người dùng hỏi "Thủ đô của Việt Nam là gì?", ChatGPT sẽ trả lời "Thủ đô của Việt Nam là Hà Nội".

**API Bard Google**

API Bard Google sẽ được sử dụng để trả lời các câu hỏi của người dùng mà không thể trả lời bằng cách tạo văn bản. Ví dụ, nếu người dùng hỏi "Số điện thoại của tổng đài điện lực là gì?", Bard Google sẽ trả lời "Số điện thoại của tổng đài điện lực là 1900 545454".

**Cài đặt**

Python là ngôn ngữ phổ biến, nhiều người hỗ trợ, dễ code dễ bảo trì. Python có rất nhiều tác dụng như dựng backend, crawler scrapy,...

Để cài đặt chatbot, cần cài đặt các thư viện sau:

```
import openai
import os
from gtts import gTTS
import speech_recognition as sr
from playsound import playsound
from pydub import AudioSegment
from pydub.playback import play
import time
from time import strftime
import yaml

```
**Chức năng chuyển văn bản thành âm thanh**

```python
def speak(data):
    global is_speaking
    try:
        # Chuyển đổi văn bản thành giọng nói
        audio = gTTS(remove_word(remove_word(data, "Thomas"), "thomas"), lang='vi')
        audio.save(str(path_file_temp))
        playsound(path_file_temp)
    except Exception as e:
        print(e)
    finally:
        print("Chuyển đổi văn bản thành giọng nói")

    return True

```

**Chạy**

Để chạy chatbot, cần khởi động chương trình sau:

<script src="https://gist.github.com/NhamNgocTuanAnh/260ebc0e582d10224d8acc0ba5a0b01f.js"></script>

```console
python chatbot.py

```

bạn có thể chạy trên jupyter python còn lập trình python mình dùng pycharm là ide của python trên windows và python tải trên pythonorg.
**Ví dụ**

Dưới đây là một ví dụ về cách chatbot trả lời câu hỏi của người dùng:

```bash
Người dùng: Thủ đô của Việt Nam là gì?
Chatbot: Thủ đô của Việt Nam là Hà Nội.
```

**Tương lai**

Chatbot có thể được cải thiện bằng cách sử dụng các kỹ thuật sau:

*   Sử dụng các mô hình ngôn ngữ lớn hơn, chẳng hạn như Megatron-Turing NLG.
*   Sử dụng các mô hình học máy tiên tiến hơn, chẳng hạn như học máy tăng cường.
*   Sử dụng các dữ liệu huấn luyện lớn hơn và đa dạng hơn.
*   loa trợ lý ảo tiếng việt

<div class="iframe-container">
  <iframe width="560" height="315" src="https://codelearn.io/sharing/lap-trinh-tro-ly-ao-tieng-viet-python" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" loading="lazy" allowfullscreen></iframe>
</div>
<a href="https://codelearn.io/sharing/lap-trinh-tro-ly-ao-tieng-viet-python" target="_blank" class="item-link item-content link external" id="facebook" onclick='getHrefOnclickAndRedirectWithLink(event)'>😍 Bài viết được tham khảo từ 1 anh VietNam</a>
<script>
var root_url=window.location.origin;function getHrefOnclickAndRedirectWithLink(t){t.preventDefault();t=t.currentTarget.getAttribute("href");window.location=[root_url,"/redirect-v2?url=",encodeURIComponent(t)].join("")}
</script>
<style>.iframe-container{overflow:hidden;padding-top:56.25%;position:relative}.iframe-container iframe{border:0;height:100%;left:0;position:absolute;top:0;width:100%}</style>



