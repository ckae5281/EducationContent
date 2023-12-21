### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Spiral

## Step 1
當Agent機器人**還沒偵測到前方是黃金方塊(Gold Block)前**，讓Agent按照下面的指示行動：<br>
・如果前方**有方塊** ，Agent機器人就要向左轉<br>
・如果前方**沒有方塊** ，Agent機器人就要向前走

當Agent機器人**偵測到前方是黃金方塊(Gold Block)** 時，就：<br>
・摧毀**黃金方塊(Gold Block)** 並收集它

```template
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) == GOLD_BLOCK) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {

        } else {
            
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```

```ghost
player.onChat("run", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.turn(LEFT_TURN)
        } else {
            agent.move(FORWARD, 1)
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```