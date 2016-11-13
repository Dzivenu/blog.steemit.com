A proof of concept blog for steem.io, built using greymass/reprint.

## Configuration

### resources/config/config.yml

```
# Choose the locale to localize content for
locale: 'en'

# Choose a theme by name
blog:
  theme: 'steem.io'
  title: 'Steem Blog'

# Blog Configuration
steem:
  # Steem Node to retreive data
  host: 'https://node.steem.ws'
  # Accounts to load activity of
  accounts:
    'steemitblog':
      - post
```

### resources/config/routes.yml

```
config.routes:
  # Homepage route to handle the options provided in the configuration
  homepage:
    name: 'homepage'
    pattern: /
    method: ['get']
    controller: 'Reprint\Controller\Home::homeAction'

  # View Post
  post_view:
    name: 'post_view'
    pattern: /{category}/@{author}/{permlink}
    method: ['get']
    controller: 'Reprint\Controller\Blog::postAction'

  # View Tagged Posts
  tag_view:
    name: 'tag_view'
    pattern: /tagged/{category}
    method: ['get']
    controller: 'Reprint\Controller\Blog::listAction'
```
