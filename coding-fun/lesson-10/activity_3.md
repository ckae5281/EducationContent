### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
當Agent機器人**偵測到下方的方塊不是冰磚(packed ice)**時，讓Agent機器人收集地圖上的**鐵方塊(iron block)**、**黃金方塊(gold block)**、**綠寶石(emerald block)**與**鑽石(diamond block)**。

試著觀察出地圖上礦石的分布與Agent機器人移動路線之間的關係

```template
player.onChat("run", function () {
    agent.setItem(STONE, 64, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) == STONE) {
        if (agent.inspect(AgentInspection.Block, DOWN) == STONE || agent.inspect(AgentInspection.Block, DOWN) == STONE ) {
            agent.turn(LEFT_TURN)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == STONE || agent.inspect(AgentInspection.Block, DOWN) == STONE ) {
            agent.turn(RIGHT_TURN)
        }
        agent.move(FORWARD, 1)
    }
})
```

```ghost
player.onChat("run", function () {
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

