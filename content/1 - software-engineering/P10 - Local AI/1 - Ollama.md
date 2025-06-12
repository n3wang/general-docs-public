
```
curl -fsSL https://ollama.com/install.sh | sh
```

```
localhost:11434
```

![[Pasted image 20250610221701.png]]


```
ollama pull llama2



ollama run llama2
```

You can also get more models on llama

```
phi3.5
```


Simple for generating and discussing code
```
codellama:latest
```

```
ollama run borch/phi3_speed_chat
```


```
stable-code:latest
```

stable-code




To look at nvidia
```
watch -n 0.5 nvidia-smi
```


### Installing MCPHost

Install go:



https://go.dev/dl/


```


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

