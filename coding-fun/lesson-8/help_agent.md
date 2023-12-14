### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Iron

## Step 1
當Agent機器人**偵測到下方有方塊**且**不是鐵礦**時就**往前移動**。

如果Agent機器人**偵測到前方有方塊**就**摧毀前方的方塊**。

如果Agent機器人找到了鐵礦，就讓它採集起來。

注意，你必須要摧毀鐵礦方塊後才能收集它。

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
