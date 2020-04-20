---
title: ubuntu 18.04 为 pillow 安装 raqm 及遇到 bug的修复
tags: linux, ubuntu, pillow, raqm
---

https://github.com/python-pillow/Pillow/issues/3066

I met this bug in ubuntu 18.04.4 LTS， after i installed raqm by apt.
Sorry that i forget the version of my pillow that time. Then i upgrade pillow by conda to 7.0.0 and found it worked well. but i realized that my libraqm version is 0.3.0 and can't work.
then i download libraqm-0.7.0 from packages.ubuntu.com and compiled it.

Now everything is OK. Hope to help someone.

error infomation followed

    File "/home/wechat/.local/lib/python3.7/site-packages/wordcloud/wordcloud.py",
        return self.generate_from_frequencies(frequencies)
    File "/home/wechat/.local/lib/python3.7/site-packages/wordcloud/wordcloud.py",
        max_font_size=self.height)
    File "/home/wechat/.local/lib/python3.7/site-packages/wordcloud/wordcloud.py",
        box_size = draw.textsize(word, font=transposed_font)
    File "/home/wechat/.local/lib/python3.7/site-packages/PIL/ImageDraw.py", line
        return font.getsize(text, direction, features, language, stroke_width)
    File "/home/wechat/.local/lib/python3.7/site-packages/PIL/ImageFont.py", line
        w, h = self.font.getsize(text)
    File "/home/wechat/.local/lib/python3.7/site-packages/PIL/ImageFont.py", line
        size, offset = self.font.getsize(text, direction, features, language)

OSError: invalid face handle
