---
layout: post
title: "Instalación de Octopress en Github"
date: 2012-06-09 14:11
comments: true
categories:
- blog
- jekyll
- configuracion
---

El primer post se dedicara a como montar un blog [octopress](http://octopress.org/) en [github](https://github.com/),
octopress permite gestionar un sitio [Jekill](http://jekyllrb.com/) mediante rake.

Para poder instalar se debe tener ruby 1.9.2, yo realicé la instalación utilizando 1.9.3 instalado mediante [RVM](https://rvm.io/).
El primer paso es clonar el repositorio de octopress e instalar las dependencias mediante Bundler

{% highlight bash %}
git clone git://github.com/imathis/octopress.git octopress
cd octopress
bundle install
{% endhighlight %}

Luego se instala el tema por defecto
{% highlight bash %}
rake install
{% endhighlight %}

Luego creamos el repositorio en github que almacenará las páginas y configuraciones del sitio por ejemplo `rarce.github.com` ,
una vez creado el repositorio ejecutamos el script de configuración, que nos preguntara por la dirección del repositorio, en
este ejemplo `git@github.com:rarce/rarce.github.com.git`

{% highlight bash %}
rake setup_github_pages
{% endhighlight %}

Esto cambiara el repositorio remoto de octopress desde origin a octopress, agregara el repositorio creado como el repositorio
remoto por defecto. Cambiará la rama activa de master a source y configurará una rama master para el directorio `_deploy`.

Luego se puede ejecutar el script para generar el sitio en jekyll y pushear la rama `master` a github

{% highlight bash %}
rake gen_deploy
{% endhighlight %}

Para subir el código, se debe hacer commit y push a la rama `source`

{% highlight bash %}
git add .
git commit -m 'your message'
git push origin source
{% endhighlight %}
 No newline at end of file
