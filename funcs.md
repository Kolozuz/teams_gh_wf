## Functions inventory

## Datetime

Current timestamp as a string
```rust
@{utcNow()}
```

UTC to SA Pacific Standard Time and General Format (Bogota, Lima, Quito)
```rust
@{convertFromUtc(utcNow(), 'SA Pacific Standard Time', 'g')}
```
	
SA Pacific Standard Time
## Github webhook body

### SenderInfo
var senderInfo
```rust
@{triggerBody()['sender']}
```

Name
```rust
@{variables('senderInfo')['login']}
```

### Repo
var repoInfo
```rust
@{triggerBody()['repository']}
```

Full name
```rust
@{outputs('repoInfo')['full_name']}
```

### Project
projectInfo
```rust
@{triggerBody()['project']}
```


```rust
@{outputs('projectInfo')['name']}
```


### Action
var actionInfo
```rust
@{triggerBody()['action']}
```


### Issues
var issueInfo
```rust
@{triggerBody()['issue']}
```

Issue Name
```rust
@{variables('issueInfo')['url']}
```

Issue Number
```rust
@{variables('issueInfo')['number']}
```

Issue Name
```rust
@{variables('issueInfo')['title']}
```

assignees
```rust
@{variables('issueInfo')['assignees']}
```

```rust
@{items('For_each_assignee')['login']}
```


labels
```rust
@{variables('issueInfo')['labels']}
```

```rs
@{items('For_each_label')['name']}
```
#### Push

head commit
```rs
@{triggerBody()['head_commit']}
```

branch ref
```rs
@{triggerBody()['ref']}
```

head commit message
```rs
@{outputs('head_commit')['message']}
```

commit url
```rs
@{outputs('head_commit')['url']}
```