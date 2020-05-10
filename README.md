## Welcome to My GitHub Page 

You can use the [editor on GitHub](https://github.com/berryq460/berryq460.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

{% comment %}
    Renders social networks sharing links.

    Parameters:
        - uses _data/social-buttons.yml file as a data source.
        - uses _includes/social-buttons folder as a souce for svg files to render.
{% endcomment %}
<div class="social-buttons">
    {% assign url_placeholder = "<url>" %}
    {% assign text_placeholder = "<title>" %}
    {% assign twitter_placeholder = "<twitter>" %}
    {% assign page_url = "https://dmitryrogozhny.com" | append: page.url | uri_escape %}

    {% for button in site.data.social-buttons %}

        {% assign button_url = button.url
                             | replace: text_placeholder, page.title
                             | replace: url_placeholder, page_url
                             | replace: twitter_placeholder, site.twitter_username
                             | uri_escape
        %}

        <a href="{{ button_url }}" target="_blank" class="social-button {{ button.title }} {% if button.noPopup != true %}js-social-buttons{% endif %}">
            <span>
                {% include social-buttons/{{ button.svg }} %}
                <span>{{ button.verb }}</span>
            </span>
        </a>
    {% endfor %}
</div>
### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/berryq460/berryq460.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
