# stasiek_selldrugsv2
Second version of Fivem selldrugs script<br>
Only you had to do is translate it ;)<br>
Fivem infinity have issues with npc spawning, soo your npc-client is spawned nearby<br>

if you've issues with ESX try adding this two functions to your es_extended/client/functions.lua<br>
```
ESX.PlayAnim = function(dict, anim, speed, time, flag)
    ESX.Streaming.RequestAnimDict(dict, function()
        TaskPlayAnim(PlayerPedId(), dict, anim, speed, speed, time, flag, 1, false, false, false)
    end)
end

ESX.PlayAnimOnPed = function(ped, dict, anim, speed, time, flag)
    ESX.Streaming.RequestAnimDict(dict, function()
        TaskPlayAnim(ped, dict, anim, speed, speed, time, flag, 1, false, false, false)
    end)
end

ESX.Game.MakeEntityFaceEntity = function(entity1, entity2)
    local p1 = GetEntityCoords(entity1, true)
    local p2 = GetEntityCoords(entity2, true)

    local dx = p2.x - p1.x
    local dy = p2.y - p1.y

    local heading = GetHeadingFromVector_2d(dx, dy)
    SetEntityHeading( entity1, heading )
end
```

# Demonstration
[![Watch the video](http://xstasiek.pl/img/stasiek31.png)](http://xstasiek.pl/video/stasiek_selldrugsv2.mp4) <- click me!
