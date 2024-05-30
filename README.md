# streamlit
银行对账单可视化工具源码 
```
# 上传并分析CSV文件
# 该部分代码用于接收用户上传的CSV文件(EXCEL表格可以另存为该格式)，并使用Pygwalker库的StreamlitRenderer组件对其进行分析。

import pandas as pd
import streamlit as st
from pygwalker.api.streamlit import StreamlitRenderer

uploaded_file = st.file_uploader("请上传您的csv文件")  # 提供文件上传界面，接收用户上传的CSV文件

if uploaded_file is not None:
    df = pd.read_csv(uploaded_file)  # 读取上传的CSV文件到DataFrame
    pyg_app = StreamlitRenderer(df)  # 使用DataFrame初始化StreamlitRenderer对象
    pyg_app.explorer()  # 启动文件分析界面

```
