### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Surroundings 

## Step 1
當Agent機器人**偵測到下方有方塊時**就向前移動，並按照下面的規則行動：

・如果Agent機器人**偵測到下方為空氣時**就使用 ''|player.say|'' 積木，並說出**Crater found!(已找到坑洞)**

```template
player.onChat("crater", function () {
            player.say("Crater found!")
})
```
```ghost
player.onChat("1", function () {
    while (agent.detect(AgentDetection.Block, DOWN)) {
        agent.move(FORWARD, 1)
    }
    if (agent.inspect(AgentInspection.Block, DOWN) == AIR) {
        player.say("Crater found!")
    }
})
```