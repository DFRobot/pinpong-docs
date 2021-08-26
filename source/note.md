# 步骤
- 安装python环境
- 安装sphinx、rest、rtdtheme

```bash
pip install sphinx==3.3.0
pip install restructuredtext-lint==1.3.1
pip install sphinx_rtd_theme==0.5.1
#修改conf.py配置主题    html_theme = 'sphinx_rtd_theme'
```

- 编译

```bash
make clean
make html
```