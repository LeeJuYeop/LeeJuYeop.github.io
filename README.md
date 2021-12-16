# Git 및 jekyll 환경 구축
블로그 구현을 위한 기초로 Git을 연결하고 jekyll을 설치.

`<username>.github.io` 이름의 repository를 생성하고 로컬저장소에 clone.

    $ git clone "https://github.com/LeeJuYeop/LeeJuYeop.github.io.git" blog

로컬저장소에 Jekyll 환경 설치:

    $ gem install jekyll bundler
    $ jekyll new . --force

# 테마 적용 및 조작
테마는 texture.

`_config.yml`을 수정하면서 테마에서 제공하는 다양한 기능을 활성화.
특히 **"texture:"** 부분이 핵심.
style은 black을 채택.
```yaml
texture:
  title: Lee's fantastic blog
  tagline: Student, Developer
  date_format: "%b %-d, %Y"
  style: [black]
  showNav : false
  showPicker : false

  social_links:
    twitter: none
    github:  LeeJuYeop
    linkedIn: in/thelehhman # format: locale/username
    rss : rss
```

post 미리보기 기능 활성화를 위해 `_config.yml`에 다음을 추가
```yaml
show_excerpts: true
```

#  댓글 기능 추가 
disqus를 이용하여 댓글 기능 추가.

`_config.yml`에 다음을 추가.
```yaml
comment:
  provider:       "disqus"
  disqus:
    shortname:    "leejuyeop"
```

_layouts 폴더의 `post.html`에 disqus에서 복사한 코드 양식을 붙여넣기
```javascript
{% if page.comments %}
    let PAGE_URL = "{{site.url}}{{page.url}}"
    let PAGE_IDENTIFIER = "{{page.url}}"
    # 붙여넣기
{% endif %}
```




# texture

A configurable jekyll theme for simply beautiful blogs.

**Demo**: [samarsault.com/texture](https://samarsault.com/texture)

![texture theme preview](/screen1.png)


## Installation on Github Pages

Add this line to your site's `_config.yml`:
```yaml
remote_theme: samarsault/texture
```

**NOTE: If you are forking this repo, remove `base_url: /texture` in the `_config.yml` which is required to load the required website assets**
## Installation

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "texture"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: texture
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install texture

## Usage

The "texture" key in _config.yml is used to customize the theme data.
```yaml
texture:
  title: Adam Denisov
  tagline: Developer. Designer
  date_format: "%b %-d, %Y"

  social_links:
    twitter: thelehhman
    github:  thelehhman
    linkedIn: in/thelehhman # format: locale/username
```

**Styling**

Multiple header styles are supported using the "style" property under texture in `_config.yml`.

```yaml
texture:
  style: [yellow|red|black|blue|green|purple]
```

For example, the blue style looks like this:

![texture theme blue](/screen2.png)


**Texture Picker**

You can toggle the texture picker to show/experiment various textures on your site using the showPicker variable. Remember to make it `false` for production.

```yaml
texture:
  showPicker: [false|true] # show the texture selector(development purposes)
```

**Comments (Disqus)**

Comments on posts can be enabled by specifying your disqus_shortname under texture in `_config.yml`. For example,
```yaml
texture:
  disqus_shortname: games
```

**Google Analytics**

It can be enabled by specifying your analytics id under texture in `_config.yml`
```yaml
texture:
  analytics_id: '< YOUR ID >'
```

**Excerpts**

Excerpts can be enabled by adding the following line to your `_config.yml`
```yaml
show_excerpts: true
```

**Toggle Navbar**

```yaml
texture:
  showNav: true
```

**Navigation**

After setting `showNav` to true navigation can be built by adding the following to your `_config.yml`

```yaml
texture:
  navigation:
    - title: My Work
      url: "/my-work"
    - title: Resume
      url: "/resume"
```

**Layouts**

- Home
- Page
- Post

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/samarsault/texture. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `texture.gemspec` accordingly.

## Donation
If this project help you reduce time to develop, you can give me a cup of coffee :) 

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://paypal.me/thelehhman)

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## More Themes
[plainwhite](https://github.com/samarsault/plainwhite-jekyll)
