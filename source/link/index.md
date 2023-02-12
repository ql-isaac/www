---
title: 友情链接
date: 2020-09-19 17:16:16
type: link
top_img: https://img.imql.life/233.jpg
---

{% issues sites | api=https://gitee.com/api/v5/repos/ql-isaac/friendly-links/issues?sort=updated&state=open&page=1&per_page=100&labels=active | group=types:个人博客,博主站点,友情链接 %}

{% btns rounded center grid5 %}
{% cell 友链申请, https://gitee.com/ql-isaac/friendly-links/issues, far fa-paper-plane %}
{% endbtns %}