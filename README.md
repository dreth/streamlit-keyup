# streamlit-keyup

[![PyPI version](https://img.shields.io/pypi/v/streamlit-keyup.svg?logo=pypi&logoColor=FFE873)](https://pypi.org/project/streamlit-keyup/)
[![PyPI downloads](https://img.shields.io/pypi/dm/streamlit-keyup.svg)](https://pypistats.org/packages/streamlit-keyup)
[![GitHub](https://img.shields.io/github/license/blackary/streamlit-keyup.svg)](LICENSE)
[![Code style: Black](https://img.shields.io/badge/code%20style-Black-000000.svg)](https://github.com/psf/black)

If you're collecting text input from your users in your streamlit app, `st.text_input` works well -- as long as you're happy with
waiting to get the response when they're finished typing.

But, what if you want to get the input out, and do something with it every time they type a new key (AKA "on keyup")?

[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://key-up.streamlitapp.com)

![filtering](https://user-images.githubusercontent.com/4040678/189153486-7ff7641c-1c76-4fa1-b0d5-f6634f8f0e41.gif)

## Installation

`pip install streamlit-keyup`

## Usage

```python
import streamlit as st
from st_keyup import st_keyup

value = st_keyup("Enter a value", key="0")

# Notice that value updates after every key press
st.write(value)

# If you want to set a default value, you can pass one
with_default = st_keyup("Enter a value", value="Example", key="1")

# If you want to limit how often the value gets updated, pass `debounce` value, which
# will force the value to only update after that many milliseconds have passed
with_debounce = st_keyup("Enter a value", debounce=500, key="2")
```
