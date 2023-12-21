### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 3d Space

## Step 1
要解決這道關卡，你需要撰寫程式讓Agent機器人能到達黃金方塊(Gold Block)前並收集它。

Agent機器人需要收集到第一層的黃金方塊(Gold Block)後，**往上移動三格**後再重複第一層的步驟來收集上層的黃金方塊(Gold Block)。

提示：仔細觀察下層與上層從起點走到黃金方塊的位置的路線，好像有一點相似喔？

```template
player.onChat("3D", function () {
    for (let index = 0; index < 2; index++) {
        
})
``` 
```ghost
player.onChat("3D", function () {
    for (let index = 0; index < 2; index++) {
        while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
            if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
            }
        }
        agent.destroy(FORWARD)
        agent.collectAll()
        agent.move(UP, 3)
    }
})
```
