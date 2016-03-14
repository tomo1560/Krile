Skip to content
This repository  
Search
Pull requests
Issues
Gist
 @monmon-map
 Watch 1
  Star 0
  Fork 0 Lunasy/village
 Code  Issues 0  Pull requests 0  Wiki  Pulse  Graphs
Branch: master Find file Copy pathvillage/xml
22d53ea  2 minutes ago
@Lunasy Lunasy Update xml
1 contributor
RawBlameHistory     130 lines (129 sloc)  5.37 KB
<?xml version="1.0" encoding="utf-8"?>
<map proto="1.3.0">
    <name>Villages</name>
    <version>1.0.8</version>
<!-- 1.0.8 MAP の修正 -->
<authors>
    <author>Lunasy_</author>
</authors>
<objective>一定時間後壁が崩壊し敵チームと戦闘に敵を殲滅せよ！/The white annihilate the enemy! Wall will after a certain time.</objective>
<teams>
  <team color="blue" max="24">Blue Team</team>
  <team color="red" max="24">Red Team</team>
</teams>
<kits>
    <kit name="spawn">
        <item slot="2" amount="64">log</item>
    </kit>
    <kit name="red" parents="spawn">
        <chestplate color="cd0000" damage="-3000">leather chestplate</chestplate>
        <leggings color="cd0000" damage="-3000">leather leggings</leggings>
        <boots color="cd0000" damage="-3000">leather boots</boots>
    </kit>
    <kit name="blue" parents="spawn">
        <chestplate color="0066cc" damage="-3000">leather chestplate</chestplate>
        <leggings color="0066cc" damage="-3000">leather leggings</leggings>
        <boots color="0066cc" damage="-3000">leather boots</boots>
    </kit>
</kits>
<classes sticky="false">
     <class name="CIVILIAN" description="You are CIVILIAN." longdescription="You have Iron Armor,Leggings,Boots,and Sword" icon="iron sword">
             <kit>
                     <item slot="0">stone sword</item>
                     <item slot="1">Stone Pickaxe</item>
                     <item slot="8" amount="16">cooked beef</item>
             </kit>
     </class>
     <class name="Miner" description="You are Miner." longdescription="You have Efficiency Pickaxe!Get more ore!" icon="Diamond Pickaxe">
             <kit>
                     <item slot="0">stone sword</item>
                     <item slot="1" enchantment="DIG_SPEED:2">Stone Pickaxe</item>
                     <item slot="8" amount="16">cooked beef</item>
             </kit>
     </class>
     <class name="Archer" description="You are Archer!" longdescription="You have bow and arrow.Aim Your Enemy!" icon="bow">
             <kit>
                     <item slot="0" enchantment="ARROW_DAMAGE:2">bow</item>
                     <item slot="1" amount="64">arrow</item>
                     <item slot="7" amount="8">Log</item>
                     <item slot="8" amount="16">cooked beef</item>
             </kit>
     </class>
     <class name="Builder" default="true" description="You are Builder!" longdescription="Build something in your base!" icon="log">
             <kit>
             <item slot="0">wood sword</item>
             <item slot="1" amount="64">Log</item>
             <item slot="2" amount="64">Log</item>
             <item slot="3" amount="64">Log</item>
             <item slot="8" amount="16">cooked beef</item>
             </kit>
     </class>
</classes>
<toolrepair>
  <tool>stone pickaxe</tool>
</toolrepair>
<renewables>
    <renewable rate="3" particles="false" sound="false" avoid-entities="false">
        <region>
            <cuboid min="297,92,655" max="404,8,530"/>
        </region>
        <renew>iron ore</renew>
        <renew>coal ore</renew>
        <renew>gold ore</renew>
        <replace>Cobblestone</replace>
    </renewable>
</renewables>
<walls drop-time="600" materials="sand">
    <cuboid min="279,95,594" max="405,49,594"/>
    <cuboid min="278,95,593" max="405,49,592"/>
</walls>
<spawns>
    <spawn team="red" yaw="0" kit="red"><cuboid min="333,55,546" max="333,54,546"/></spawn>
    <spawn team="blue" yaw="178" kit="blue"><cuboid min="333,54,640" max="333,55,640"/></spawn>
    <default yaw="90"><cuboid min="431,126,594" max="431,127,594"/></default>
</spawns>
<shops>
  <shop name="Weapon">
    <item price="coal block,1" slot="0">iron sword</item>
    <item price="coal block,1" slot="5" amount="16">arrow</item>
    <item price="coal block,3" slot="1" enchantment="KNOCKBACK:1">iron sword</item>
    <item price="coal block,3" slot="2" enchantment="ARROW_KNOCKBACK:1">bow</item>
    <item price="coal block,3" slot="6" amount="3">golden apple</item>
    <item price="coal block,4" slot="3" enchantment="FIRE_ASPECT:1">iron sword</item>
    <item price="coal block,4" slot="4" enchantment="ARROW_FIRE:1">bow</item>
  </shop>
</shops>
<shops>
  <shop name="CAFE">
    <item price="gold ingot,1" slot="1">Baked Potato</item>
    <item price="gold ingot,1" slot="2">Cooked Fish</item>
    <item price="gold ingot,1" slot="3">Water Bucket</item>
  </shop>
</shops>
<killreward>
     <item amount="1">diamond</item>
</killreward>
<regions>
        <apply message="範囲外のブロックは破壊できません / Outside the scope of the block can not be destroyed" block="deny-all">
        <cuboid max="404,94,656" min="404,9,531"/>
                <cuboid max="404,9,531" min="278,94,531"/>
                <cuboid max="278,94,531" min="278,9,656"/>
                <cuboid max="278,9,656" min="404,9,656"/>
                <cuboid min="279,95,594" max="405,49,594"/>
    </apply>
</regions>


<!-- 多言語化 by monmon -->
<locales>
    <locale lang="ja_JP">
    <string name="Outside the scope of the block can not be destroyed" value="範囲外のブロックは破壊できません。"/>
    </locale>
</locales>


<maxbuildheight>92</maxbuildheight>
    <include src="tutorial.xml"/>
    <tutorial>
        <stage title="The Walls">
            <message>
                <line>This is Walls map.</line>
                <line>The objective is killing your enemy.</line>
            </message>
            <message lang="ja_JP">
                <line>このMAPは Wallsのマップです。</line>
                <line>敵チームを全滅させることが目的です。</line>
            </message>
        </stage>
    </tutorial>
</map>
Status API Training Shop Blog About Pricing
© 2016 GitHub, Inc. Terms Privacy Security Contact Help
