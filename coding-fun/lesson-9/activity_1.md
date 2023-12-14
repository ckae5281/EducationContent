### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Locating stone 

## Step 1
修正下面的程式碼，讓Agent機器人完成以下的步驟: 

**往左移動4格**，**摧毀下方方塊**，**往下移動**。

 如果Agent機器人偵測到前方有**石磚方塊**，就說出「**Found the stone!**」，接著摧毀石磚方塊並收集。

 如果Agent沒有偵測到有石磚方塊，就說出「**No stone here!**」，接著**往上移動一格**回到表面。

 以上的動作需要重複**4**次。

```template
player.onChat("stone", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(RIGHT, 4)
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) != STONE) {
            player.say("Found the stone!")
            agent.destroy(FORWARD)
            agent.collectAll()
        } else {
            player.say("No stone here!")
        }
        agent.move(UP, 1)
    }
})
```
