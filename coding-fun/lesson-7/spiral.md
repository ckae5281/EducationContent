### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Spiral

## Step 1
當Agent機器人<strong>還沒偵測到前方是黃金方塊(Gold Block)前</strong>，讓Agent按照下面的指示行動
<li>如果前方<strong>有方塊</strong>，Agent機器人就要向左轉</li>
<li>如果前方<strong>沒有方塊</strong>，Agent機器人就要向前走</li>
當Agent機器人<strong>偵測到前方是黃金方塊(Gold Block)</strong> 時，就：  
<li>摧毀黃金方塊(Gold Block)並<strong>收集它</strong></li>

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
