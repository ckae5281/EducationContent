### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Reach magma

## Step 1
撰寫程式，先讓Agent機器人**向前移動一步**，離開鑽井平台。

接著，在Agent機器人**還沒偵測到下方是岩漿(Magma)前不斷往下移動**，<br>如果**偵測到下方是岩漿(Magma)**就立刻停下來


```ghost
player.onChat("magma", function () {
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != MAGMA_BLOCK) {
        agent.move(DOWN, 1)
    }
})
```

