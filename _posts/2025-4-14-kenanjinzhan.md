---
layout: post
title: "一些debug问题"
date:   2024-1-27
tags: [tag1]
comments: true
author: xxx
---
huggingface git不成功，提示repos public gated，原因是在生成token时没有将access public gated repos勾选上，重新选定生成新token，用户名为Kiki313，git下来即可
torch.hub.load 加载zeodepth预训练参数不成功，提示http 403，原因是torch.hub.load的访问流程是先访问github，然后在username/.cache/torch/hub/checkpoint寻找有没有预训练参数，github封了中国ip，出现了403
如需手动加载，首先git下模型，实例化模型，torch.load参数
或者沿用torch.hub.load,修改hubconf文件
torch.hub.load报错core dump原因是torch版本不匹配，换个torch版本就ok了
