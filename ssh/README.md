# SSH keys 

### Create SSH key usable for github and other services

```keygen -f ~/.ssh/id_username```

### List SSH keys held by ssh-agent
```ssh-add -l```

### Start ssh-agent
```eval "$(ssh-agent -s)"```

### Add key to ss-agent
```ssh-add ~/.ssh/id_new_key```


