# 步骤
- 安装python环境
- 安装sphinx、rest、rtdtheme

```bash
pip install sphinx
pip install restructuredtext-lint
pip install sphinx_rtd_theme
#修改conf.py配置主题    html_theme = 'sphinx_rtd_theme'

```
- 实时预览
```bash
pip install sphinx-autobuild
sphinx-autobuild source build/html
#127.0.0.1:8000
```

- 编译

```bash
make clean
make html
```