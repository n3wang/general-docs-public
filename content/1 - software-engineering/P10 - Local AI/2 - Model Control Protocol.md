
Install go:

https://go.dev/dl/


```sh
cd /tmp
curl -LO https://go.dev/dl/go1.24.4.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.24.4.linux-amd64.tar.gz


go install github.com/mark3labs/mcphost@latest







ls $HOME/go/bin/mcphost


$HOME/go/bin/mcphost --system-prompt "You are a helpful assistant that responds in a friendly tone."



```



```
mcphost --system-prompt ./my-system-prompt.json
```

```json
{
  "mcpServers": {
    "sqlite": {
      "command": "uvx",
      "args": [
        "mcp-server-sqlite",
        "--db-path",
        "/tmp/foo.db"
      ]
    },
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/tmp"
      ],
      "allowedTools": ["read_file", "write_file"],
      "excludedTools": ["delete_file"]
    }
  }
}
```


npx

```json
{
  "mcpServers": {
    "sqlite": {
      "command": "uvx",
      "args": [
        "mcp-server-sqlite",
        "--db-path",
        "/tmp/foo.db"
      ]
    },
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/tmp"
      ],
      "allowedTools": ["read_file", "write_file"],
      "excludedTools": ["delete_file"]
    }
  }
}
```

mcphost --system-prompt ./my-system-prompt.json


```
$HOME/go/bin/mcphost --config mcp.config.json
```



```
$HOME/go/bin/mcphost -m ollama:phi3.5 --config mcp.config.json
```


```
$HOME/go/bin/mcphost -m ollama:llama2 --config mcp.config.json
```



### Using Visual Clients

- Does ollaa visual client support this?


Lets say

http://github.com/open-webui/open-webui


- well since, this can be 

```
$HOME/go/bin/mcphost -m ollama:qwen2.5 --config mcp.config.json
```



## Simple Click and Build 



