### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Track Down the Rover 

## Step 1
修正下面的程式碼，讓Agent機器人完成以下的目標: 

當Agent機器人偵測前方時沒有偵測到**石英方塊**就往前移動，

如果Agent機器人偵測下方時偵測到**黃金方塊**就向右轉，

如果Agent機器人偵測下方時偵測到**鐵方塊**就向左轉。

在程式的最後要讓Agent機器人說出「**Found the rover!(找到探測車了)**」

```template
player.onChat("rover", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != BLOCK_OF_QUARTZ) {
            if (agent.inspect(AgentInspection.Block, UP) == GOLD_BLOCK) {
            agent.turn(LEFT_TURN)
        }
            if (agent.inspect(AgentInspection.Block, RIGHT) == IRON_BLOCK) {
            agent.turn(RIGHT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the rover!")
})
```

