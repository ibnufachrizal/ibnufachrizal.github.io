---
layout: post
title:  "Github Pages dan Jekyll"
author: ibnu
categories: [ info ]
image: assets/images/github1.jpg

beforetoc: ""
toc: true
---
Hosting sudah sangat murah, lebih dari itu VPS pun juga tidak mahal, tapi ada yang lebih murah, hosting gratis di Github Pages. OK, mungkin banyak yang berfikir akan pusing menulis file html murni, nah itu ada solusinya, yaitu menggunakan jekyll, yang sudah terintegrasi dengan Github Pages. Yuk, ini catatan kecil saya tentang Github Pages dan Jekyll, selamat menikmati.

Masih agak bingung dari mana memulai, he...he..

Buat Repository dengan nama username.github.io

![Gambar1](/assets/images/github2.jpg)

Clone Repository baru tadi ke laptop

{% highlight bash %}
ibnu@E202SA:~/tmp$ git clone git@github.com:ibnufachrizal/ibnufachrizal.github.io.git
Cloning into 'ibnufachrizal.github.io'...
remote: Enumerating objects: 38, done.
remote: Counting objects: 100% (38/38), done.
remote: Compressing objects: 100% (25/25), done.
remote: Total 297 (delta 19), reused 32 (delta 13), pack-reused 259
Receiving objects: 100% (297/297), 1.02 MiB | 300.00 KiB/s, done.
Resolving deltas: 100% (121/121), done.
{% endhighlight %}


Install jekyll di laptop

{% highlight bash %}
ibnu@E202SA:~/tmp$ sudo apt-get install jekyll
{% endhighlight %}

Buat project jekyll dengan nama web

{% highlight bash %}
ibnu@E202SA:~/tmp$ jekyll new web
New jekyll site installed in /home/ibnu/tmp/web.
ibnu@E202SA:~/tmp$ ls
ibnufachrizal.github.io  web
{% endhighlight %}

Copy isi folder web ke folder ibnufachrizal.github.io

Masukkan file baru ke repository

{% highlight bash %}
ibnu@E202SA:~/tmp/ibnufachrizal.github.io$ git add --all
ibnu@E202SA:~/tmp/ibnufachrizal.github.io$ git commit --all -m "OK"
ibnu@E202SA:~/tmp/ibnufachrizal.github.io$ git push
{% endhighlight %}

Pengaturan Domain, buat alias pada domain untuk mengarah ke ibnufachrizal.github.io

![Gambar2](/assets/images/domain1.png)

Setting alias pada repository

![Gambar3](/assets/images/github3.jpg)

**Fitur lain Jekyll**

- Generate seluruh website untuk di letakkan di Apache Root Directory

Kita bisa menggunakan perintah build, sehingga seluruh website
di generate dan tinggal meletakkan folder tersebut di Apache Root Direktory.
Contoh penggunaannya:

{% highlight text %}
$ ~/.gem/ruby/2.6.0/bin/jekyll build -d www.ibnufachrizal.id
Configuration file: /home/ibnu/working/ibnufachrizal.github.io/_config.yml
            Source: /home/ibnu/working/ibnufachrizal.github.io
       Destination: /home/ibnu/working/ibnufachrizal.github.io/www.ibnufachrizal.id
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 3.921 seconds.
 Auto-regeneration: disabled. Use --watch to enable.
{% endhighlight %}

- Serve Jekyll dengan local webservice

Jekyll datang dengan webserver bawaannya, yang bisa kita gunakan 
untuk mengetest hasil editan/postingan kita, sebelum di publish
di internet. Kita bisa mengakses ke http://localhost:4000

Berikut ini contohnya:

{% highlight text %}
$ ~/.gem/ruby/2.6.0/bin/jekyll serve --trace
Configuration file: /home/ibnu/working/ibnufachrizal.github.io/_config.yml
            Source: /home/ibnu/working/ibnufachrizal.github.io
       Destination: /home/ibnu/working/ibnufachrizal.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 4.333 seconds.
 Auto-regeneration: enabled for '/home/ibnu/working/ibnufachrizal.github.io'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
{% endhighlight %}

Sekian dan semoga bermanfaat.

Daftar Pustaka

1. [Github Pages Jekyll](https://www.google.com/search?q=github+pages+jekyll)