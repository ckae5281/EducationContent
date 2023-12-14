### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Reach magma

## Step 1
撰寫程式，先讓Agent機器人**向前移動一步**。
接著，當Agent機器人**偵測到下方方塊不是岩漿(Magma)時**就**往下移動**，直到偵測到岩漿(Magma)


```ghost
player.onChat("magma", function () {
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != MAGMA_BLOCK) {
        agent.move(DOWN, 1)
    }
})
```

