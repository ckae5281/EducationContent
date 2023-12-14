### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
當Agent機器人**偵測到下方的方塊不是冰磚(packed ice)**時，讓Agent機器人收集地圖上的**鐵礦(iron)**、**黃金(gold)**、**綠寶石(emerald)**與**鑽石(diamond)**。

試著觀察出地圖上礦石的分布與Agent機器人移動路線之間的關係

```ghost
player.onChat("3", function () {
    agent.setItem(STONE, 64, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != PACKED_ICE) {
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON || agent.inspect(AgentInspection.Block, DOWN) == GOLD) {
            agent.turn(LEFT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == DIAMOND || agent.inspect(AgentInspection.Block, DOWN) == EMERALD) {
            agent.turn(RIGHT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
```

