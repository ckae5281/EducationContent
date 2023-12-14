### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Spiral

## Step 1
當Agent機器人**偵測到前方不是黃金方塊**時，如果前方**有方塊**，Agent機器人就要向左轉；如果前方**沒有方塊**，Agent機器人就要向前走。

當Agent機器人**偵測到前方是黃金方塊**時，Agent機器人就需要**摧毀**並**收集**黃金方塊。

```ghost
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```
