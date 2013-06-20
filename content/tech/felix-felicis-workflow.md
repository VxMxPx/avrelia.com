# Felix Felicis Workflow

- slug: felix-felicis-workflow
- date: 2013-03-27
- category: tech
- tags: python, www-dev
- source: http://jinja.pocoo.org/docs/ ||
          http://docs.sublimetext.info/en/latest/reference/snippets.html ||
          http://www.sublimetext.com/forum/viewtopic.php?f=2&t=5550#p24913 ||
          http://sublimetext.userecho.com/topic/29384-is-it-possible-to-execute-a-command-instead-of-inserting-content-for-snippets/

-------------------

Beside setting up webhook, which allowing this blog to regenerate itself whenever I
push new changes to [GitHub](https://github.com/VxMxPx/avrelia.com), I've made some further customizations to make my life easier.

## Template Customizations

Added support for sources, which can be used in following way:

    - source: http://url.one ||
              http://url.two ||
              http://url.three

To achieve this functionality, in your template folder modify file `filters.py`
and add:

````python
def split_soruces(sources):
    return sources.split('||')
````

...and then in `templates\post.html` add:

````jinja
{%if post.source%}
    {% set post_source = post.source|split_soruces %}
    <br><span class="entry-meta">Sources:</span>
    {% for source in post_source -%}
        <br><a href="{{source}}">{{source}}</a>
    {%- endfor %}
{%endif%}
````

## Sublime Text Snippet and Date Plugin

In Sublime Text editor, I've added plug-in which allows me to add current date (saved it as date.py) 
by entering: YYYY-MM-DD:

````python
import sublime_plugin
import datetime

class DateCompleter(sublime_plugin.EventListener):
    def on_query_completions(self, view, prefix, locations):
        return [
            ("YYYY-MM-DD", str(datetime.date.today())),
            ("YYYY", str(datetime.date.today().year)),
            ("MM", "%2d" % datetime.date.today().month),
            ("DD", "%2d" % datetime.date.today().day)
        ]
````

And finally, I've added a snippet to be able to create a new post quickly.<br>
_The slug will be auto generated from post's title, as you type._

````xml
<snippet>
    <content><![CDATA[
# ${1:Post Title}

- slug: ${1/(\w+)(?:(\s+?)|\b)/?1:\L$1(?2:-)\E/g}
- date: ${2:YYYY-MM-DD}${3}
- tags: ${4}
${5:- source: ${6}}

-----------------

${7}

]]></content>
    <!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
    <tabTrigger>post</tabTrigger>
    <!-- Optional: Set a scope to limit where the snippet will trigger -->
    <scope>text.html.markdown</scope>
</snippet>
````