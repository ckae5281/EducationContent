### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Deep Stone 

## Step 1
修正下面的程式碼，讓Agent機器人完成以下的步驟: 

向下鑽入地表，直到**偵測到左側有黃金方塊(gold block)**，

在鑽下去的過程中，Agent機器人會偵測**前方**是否有**石磚(stone)**，如果有就破壞並收集起來。

```template
player.onChat("dig", function () {
    while (agent.inspect(AgentInspection.Block, LEFT) == AIR) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
            if (agent.inspect(AgentInspection.Block, FORWARD) != GRASS) {
                player.say("Found the stone!")
                agent.destroy(FORWARD)
                agent.collectAll()
        }
    }
})
```


