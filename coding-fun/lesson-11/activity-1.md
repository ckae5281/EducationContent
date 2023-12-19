### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Planet visit

## Step 1
下面有編號1到3的程式，它們都是正確的所以不需要進行修改，

你需要做的是仔細觀察程式碼，試著找出適合這次任務的程式碼並執行它。

注意：你在這次任務只有一次機會可以嘗試，請務必仔細觀察並謹慎挑選。



```template
player.onChat("1", function () {
    for (let index = 0; index < 28; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 8; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 24; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
player.onChat("2", function () {
    for (let index = 0; index < 10; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 4; index++) {
                agent.move(FORWARD, 1)
                agent.setItem(PLANKS_OAK, 1, 1)
                agent.place(DOWN)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_ORE) {
            agent.turn(RIGHT_TURN)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE) {
            agent.turn(LEFT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found Ore Deposit!")
})
```
```ghost
player.onChat("1", function () {
    for (let index = 0; index < 28; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 8; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
    for (let index = 0; index < 24; index++) {
        if (agent.detect(AgentDetection.Block, FORWARD) || (agent.detect(AgentDetection.Block, LEFT) || agent.detect(AgentDetection.Block, RIGHT))) {
            agent.destroy(FORWARD)
            agent.destroy(LEFT)
            agent.destroy(RIGHT)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
player.onChat("2", function () {
    for (let index = 0; index < 10; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 4; index++) {
                agent.move(FORWARD, 1)
                agent.setItem(PLANKS_OAK, 1, 1)
                agent.place(DOWN)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == GOLD_ORE) {
            agent.turn(RIGHT_TURN)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE) {
            agent.turn(LEFT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found Ore Deposit!")
})
```

