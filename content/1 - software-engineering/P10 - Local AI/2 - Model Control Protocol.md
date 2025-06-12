
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



## Plugging other models


![[Pasted image 20250612044202.png]]

>Here you can see that it uses claude, but there is a problem, to replace it it has to follow (or at least have the wrapper for messages.create something)

![[Pasted image 20250612044414.png]]


Lets inspect ollamaccp code by 


Lets see what has to be mocked or replaced on that class

![[Pasted image 20250612044829.png]]

![[Pasted image 20250612045034.png]]
Lets see

```
{
  "messages": [
    {
      "role": "user",
      "content": "show me the table availables in the db"
    }
  ]
}
```


```
INFO: Started server process [154737]  
INFO: Waiting for application startup.  
[06/12/25 04:49:24] INFO Processing request of type ListToolsRequest server.py:558  
  
Connected to 'weather' with tools: ['get_alerts', 'get_forecast', 'get_joke', 'get_reporters_names']  
[06/12/25 04:49:24] INFO Processing request of type ListToolsRequest server.py:558  
  
Connected to 'calculator' with tools: ['get_evaluate_expression']  
  
Connected to 'sqlite' with tools: ['read_query', 'write_query', 'create_table', 'list_tables', 'describe_table', 'append_insight']  
INFO: Application startup complete.  
  
MCP Client Started!  
response called in process query Message(id='msg_01PYZdjQzkTXgn7d5AtCa7mr', content=[TextBlock(citations=None, text="I'll help you list all the tables in the SQLite database using the `list_tables` function.", type='text'), ToolUseBlock(id='toolu_01KZmWcJqWiYxDDDsaEEPsX8', input={}, name='list_tables', type='tool_use')], model='claude-3-5-sonnet-20241022', role='assistant', stop_reason='tool_use', stop_sequence=None, type='message', usage=Usage(cache_creation_input_tokens=0, cache_read_input_tokens=0, input_tokens=1137, output_tokens=59, server_tool_use=None, service_tier='standard')) [Message(role='user', content='show me the table availables in the db')]  
=====  
Message(id='msg_01PYZdjQzkTXgn7d5AtCa7mr', content=[TextBlock(citations=None, text="I'll help you list all the tables in the SQLite database using the `list_tables` function.", type='text'), ToolUseBlock(id='toolu_01KZmWcJqWiYxDDDsaEEPsX8', input={}, name='list_tables', type='tool_use')], model='claude-3-5-sonnet-20241022', role='assistant', stop_reason='tool_use', stop_sequence=None, type='message', usage=Usage(cache_creation_input_tokens=0, cache_read_input_tokens=0, input_tokens=1137, output_tokens=59, server_tool_use=None, service_tier='standard'))  
[06/12/25 04:49:38] INFO Processing request of type ListToolsRequest server.py:558  
[06/12/25 04:49:38] INFO Processing request of type ListToolsRequest server.py:558  
response called inside tool use with Message(id='msg_018rY4kC1BSgJwmPfq8jtXUv', content=[TextBlock(citations=None, text='There are two tables in the database:\n1. messages\n2. users\n\nWould you like to see the schema (structure) of any of these tables? I can help you with that using the `describe_table` function.', type='text')], model='claude-3-5-sonnet-20241022', role='assistant', stop_reason='end_turn', stop_sequence=None, type='message', usage=Usage(cache_creation_input_tokens=0, cache_read_input_tokens=0, input_tokens=1223, output_tokens=52, server_tool_use=None, service_tier='standard')) [Message(role='user', content='show me the table availables in the db'), {'role': 'assistant', 'content': [TextBlock(citations=None, text="I'll help you list all the tables in the SQLite database using the `list_tables` function.", type='text'), ToolUseBlock(id='toolu_01KZmWcJqWiYxDDDsaEEPsX8', input={}, name='list_tables', type='tool_use')]}, {'role': 'user', 'content': [{'type': 'tool_result', 'tool_use_id': 'toolu_01KZmWcJqWiYxDDDsaEEPsX8', 'content': [TextContent(type='text', text="[{'name': 'messages'}, {'name': 'users'}]", annotations=None)]}]}]  
=====  
Message(id='msg_018rY4kC1BSgJwmPfq8jtXUv', content=[TextBlock(citations=None, text='There are two tables in the database:\n1. messages\n2. users\n\nWould you like to see the schema (structure) of any of these tables? I can help you with that using the `describe_table` function.', type='text')], model='claude-3-5-sonnet-20241022', role='assistant', stop_reason='end_turn', stop_sequence=None, type='message', usage=Usage(cache_creation_input_tokens=0, cache_read_input_tokens=0, input_tokens=1223, output_tokens=52, server_tool_use=None, service_tier='standard'))  
INFO: 127.0.0.1:51258 - "POST /chat HTTP/1.1" 200 OK
```

Ok so the blocker here is that you have to create an modle that can support returning using the TextContent and Blocks


![[Pasted image 20250612045741.png]]


