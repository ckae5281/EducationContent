### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
當Agent機器人**偵測到下方的方塊是冰磚(packed ice)**時，如果**偵測到右邊有方塊**就往前移動，否則就**向右移動**。

```ghost
player.onChat("1", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
    }
})
```

