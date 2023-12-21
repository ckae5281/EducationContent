### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Iron

## Step 1
當Agent機器人**偵測到下方有鐵礦(Iron ore)以外的方塊**時就**往前移動**，並按照下面的規則行動：

・如果Agent機器人**偵測到前方有方塊**就**摧毀前方的方塊**。

・如果Agent機器人**偵測到下方有鐵礦方塊(Iron ore)**，就把它採集起來。

提示：所有的方塊都要先破壞後才能採集，你可以嘗試這麼做：
```block
if (agent.inspect(AgentInspection.Block, DOWN) == "鐵礦方塊(Iron ore)的積木") {
        agent.destroy(DOWN)
        agent.collectAll()
    }
```

```ghost
player.onChat("4", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != IRON_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the iron ore!")
    agent.destroy(DOWN)
    agent.collectAll()
})
```
