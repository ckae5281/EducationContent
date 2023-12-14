### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Repair the Rover 

## Step 1
修正下面的程式碼，讓Agent機器人完成以下的目標: 

當Agent機器人**偵測前方時沒有偵測到空氣**，就向右移動。

當Agent機器人**偵測前方時偵測到青金石(lapis lazuli)**，就向右移動，向左轉，再向右移動，

接著會說出「**Found the break!(找到故障了)**」，並**在前方放置一塊紅石磚塊(redstone block)**


```template
player.onChat("repair", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) == AIR) {
        agent.move(RIGHT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == LAPIS_LAZULI_BLOCK) {
            agent.move(RIGHT, 1)
            agent.turn(RIGHT_TURN)
            agent.move(LEFT, 1)
        }
    }
    player.say("Found the break!")
    agent.setItem(GRASS, 1, 1)
    agent.place(FORWARD)
})
```
