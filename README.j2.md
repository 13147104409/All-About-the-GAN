# All-About-the-GAN

### GAN(Generative Adversarial Networks) are the models that used in unsupervised machine learning, implemented by a system of two neural networks competing against each other in a zero-sum game framework. It was introduced by Ian Goodfellow et al. in 2014.

The purpose of this repository is providing the summarized list of the state-of-the-art works on the field of Generative Adversarial Networks since their introduction in 2014.

It provides a list that merged information from various GAN lists and repositories as below:

### :link: Reference repositories
* [[GAN zoo]](https://github.com/hindupuravinash/the-gan-zoo) - A list of all named GANs! by hindupuravinash
* Delving deep into Generative Adversarial Networks (GANs) [[Delving]](https://github.com/GKalliatakis/Delving-deep-into-GANs)
* Awesome GAN for Medical Imaging by GKalliatakis [[Medical]](https://github.com/xinario/awesome-gan-for-medical-imaging/) by xinario
* [[Adversarial Nets Papers]](https://github.com/zhangqianhui/AdversarialNetsPapers/) The classic about Generative Adversarial Networks
* [[Really Awesome GAN]](https://github.com/nightrome/really-awesome-gan) by nightrome
* [[GANs Paper Collection]](https://github.com/shawnyuen/GANsPaperCollection) by shawnyuen
* Collection of generative models in [[Pytorch version]](https://github.com/znxlwm/pytorch-generative-model-collections), [[Tensorflow version]](https://github.com/hwalsuklee/tensorflow-generative-model-collections), [[Chainer version]](https://github.com/pfnet-research/chainer-gan-lib)

----

You can also check out the same data in a tabular format with functionality to filter by year or do a quick search by title [here](https://github.com/hollobit/All-About-the-GAN/blob/master/AllGAN-r2.tsv).

Contributions are welcome. Please contact me at hollobit@etri.re.kr or send a pull request. You can have to add links through pull requests or create an issue which something I missed or need to start a discussion.

----

{% set count = {'value': 1} %}
{% for gan in gans %}
 {{count.value}}. {{ gan['Title'] }} ( {{ gan['Abbr.'] }} ) -   ([Search](http://www.google.com/search?q={{ gan['Title']|urlencode() }}))  ([Scholar](http://scholar.google.com/scholar?q={{ gan['Title']|urlencode() }}))   ([PDF]({{ gan['pdf'] }}))
  {% if count.update({'value': (count.value + 1)}) %} {% endif %}
  {%- if gan['Arxiv'] != '-' and gan['Arxiv'] != '' -%}
  {#- #} ([arXiv]({{ gan['Arxiv'] }}))
  {% else %} {# space removed if no arxiv repository #}
  {% endif %}

  {%- if gan['Official_Code'] != '-' and gan['Official_Code'] != '' -%}
  {#- #} ([github]({{ gan['Official_Code'] }}))
  {% else %} {# space removed if no github repository #}
  {% endif %}

  {%- if gan['Medical'] != '-' -%}
  {#- #} > - `{{ gan['Year'] }}/{{ gan['Month'] }}` `Citation: {{ gan['Citations'] }}` __`Medical: {{ gan['Medical'] }}`__

  {% elif gan['Category'] != '-' %}
  {#- #} > - `{{ gan['Year'] }}/{{ gan['Month'] }}` `Citation: {{ gan['Citations'] }}` `{{ gan['Category'] }}`  

  {% else %} {# space removed if no github repository #}
  {#- #} > - `{{ gan['Year'] }}/{{ gan['Month'] }}` `Citation: {{ gan['Citations'] }}`

  {% endif %}  

{%- endfor %}

----

#### GAN counter: {{ count.value-1 }}

#### Modified: {{ nowts.strftime('%A, %b %d %Y / %X') }}

MIT (c) 2017, 2018 Jonathan Jeon
