### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Simulation  

## Step 1
歡迎來到模擬空間！你可以在這裡撰寫程式操控你的Agent機器人收集**黃金方塊**，並摧毀路途中的障礙物。

```template
player.onChat("simulations", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (agent.inspect(AgentInspection.Block, LEFT) == GOLD_BLOCK) {
        	
        }
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.turn(LEFT_TURN)
        }
    }
})

```
```ghost
player.onChat("5", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (agent.inspect(AgentInspection.Block, LEFT) == GOLD_BLOCK) {
            agent.destroy(LEFT)
            agent.collectAll()
        }
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.turn(LEFT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```
