### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Locate the Sample! 

## Step 1
・當Agent機器人**偵測到下方有藍冰(Blue Ice)以外的方塊**時，讓Agent機器人**摧毀下方的方塊**並**向下移動**。

・當Agent機器人**偵測到下方有藍冰(Blue Ice)時**時, 讓Agent機器人**摧毀下方的方塊**並**收集藍冰(Blue Ice)**。

```ghost 
player.onChat("ice", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != ICE) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
    }
    agent.destroy(DOWN)
    agent.collectAll()
    
})
```

