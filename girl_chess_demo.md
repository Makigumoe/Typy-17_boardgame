# 大概是美少女兵棋

（初步设想：侦察，攻击，共享情报）

## 1 战斗单位

地图上，最基本的作战单元是单位（Unit）。一个单位由一个或多个的步兵或载具构成，它们以单位为整体进行行动。步兵与载具的差距非常大，下面分开进行描述。

### 1.1 步兵

步兵是战斗的核心，即使是载具，也需要步兵作为乘员进行操纵。当一方丧失了所有的步兵（含载具的乘员）时，认为是被彻底歼灭，失败。

#### 1.1.1 基本属性

Hit Point，HP：承受伤害的能力。当HP为0时，步兵阵亡。

Movement，M：移动能力，是一次移动中能消耗的最大移动点数。

Armor，ARM：护甲值，用于判定一次攻击是否击穿，未能击穿的攻击是无效的。

Ranged Combat，RC：远距离战斗能力，描述了步兵射击远程武器的基本精确度。

Close Combat，CC：近距离战斗能力，描述了步兵近距离格斗的能力。

Awareness，AW：态势感知能力，对战场态势更敏锐的人可以先发制敌，也可以更好的进行战场通信。

Optical Reconnaissance，OR：光学侦察能力。

Optical Signature，OS：光学特征，受光学侦查时的易暴露程度。

Electrical Reconnaissance，ER：电子侦察能力。

Electromagnetic Signature，ES：电磁特征，受电子侦察时的易暴露程度。

Terrain Adaptation，TA：地形适应性，详细给出在各类地形上移动所消耗的移动点数。

Points，Pt：分值，组建军表时用总分值来限制上场的单位数量。

#### 1.1.2 其他属性

Action Point，AP：行动点，用于主动回合中执行行动。在单位的回合开始时，除非有特殊说明，AP回复到2。

Reaction Point，RP：反应点，用于非主动回合中执行反应。在单位的回合开始时，除非有特殊说明，RP回复到1。

Special Weapon Slots，SWS：特武槽位，决定了最大能携带多少特武。

Tactical Accessory Slots，TAS：战术道具槽位，决定了最大能携带多少战术道具。

Squad Organization，SO：单位编制，描述了单位最多能包含多少步兵。单位中步兵的总HP不能超过SO。

Intelligence，Intel：情报值，表现了敌方对该单位的情报掌握程度，在战斗开始时初始情报值为0。

#### 1.1.3 选配装备

**选择武器** 一个步兵必须从她可以选择的普通武器中选择至少一项。一般而言，一个步兵只能有一项普通武器，但近战武器除外，在对战双方同意的情况下也可以选择多项普通武器。但是，无论具有多少普通武器，在一次射击/近战行动中，一个步兵只能使用其中的一项进行攻击。此外，她还可以从能选择的特殊武器中进行选取，但需要满足SPS的限制，详细规定见组成单位一节。

**选择护甲** 护甲不是必选项，但一般而言步兵都装备了护甲。护甲主要提高了步兵的ARM，令各类武器在命中时更难击穿，从而提高步兵的存活能力。

**选择战术道具** 战术道具不是必选项，但战术道具可以提高步兵应对各种情况的能力。选择战术道具时需要满足TAS的限制。

#### 1.1.4 组成单位

多个步兵组成一个单位，作为一个整体进行行动。一般而言，单位中的步兵的各项属性应当一致，从而更方便进行结算。在少数不一致的情况下，单位作为一个整体，基本属性的调整原则为：

* M，ARM取各步兵中的最低值。
* AW，OR，OS，ER，ES，TA取各步兵中的最高值。
* HP，RC，CC依旧保留。也就是说，在结算攻击命中时，各步兵用他们自己的RC/CC作为判定根据。在结算步兵阵亡时，不同步兵的HP也分别结算。
* 对各步兵的Pt求和，得出单位的Pt。

当单位中存在属性不一致的步兵时，随着单位承受伤亡，属性也可能发生相应变化。因此推荐用属性一直的步兵组成单位。

此外，单位具有两项属性：SWS和TAS。单位中每存在一个步兵，就获得1SWS和2TAS。因此当单位承受伤亡，SWS和TAS也随之下降。如果单位携带的特殊武器或战术道具超过了SWS和TAS的限制，那么就必须丢弃掉一部分，从而满足限制。控制承受伤亡单位的玩家选择丢弃掉哪些特殊武器或战术道具。

举例：由3名改造人类组成的单位装备3把电浆步枪，总点数为3，SWS也刚好为3，满足限制。在随后战斗中，一名改造人类阵亡，SWS随之降低为2，必须将特殊武器总点数降低到2以下，因此丢弃1把电浆步枪。

#### 1.1.5 英雄人物

考虑到卖点毕竟是美少女（？），所以有英雄人物这个概念。一般来讲，英雄往往比她的同侪更为坚韧顽强，在游戏属性上则表现为HP+1。举例，改造人类的HP为2，而以为改造人类英雄的HP为3。

除此之外，英雄人物还有一项属性，Leadership，LD。LD决定了这位英雄所领导的单位人数，也即是说，在英雄领导下的单位的SO等于英雄的LD。这使得某些英雄可以带领比一般情况更多的战斗人员进行战斗。

#### 1.1.6 步兵单位示例

<table>
  <tr>
    <th colspan=6 align="center">战术人形小队（M4A1）</th>
    <th>?? Pt</th>
  </tr>
  <tr>
    <th colspan=7 align="center">战斗属性</th>
  </tr>
  <tr>
    <th>AP</th>
    <td colspan=3>○○</td>
    <th>RP</th>
    <td colspan=2>○</td>
  </tr>
  <tr>
    <th>HP</th>
    <td colspan=6 align="center">○○○|○○|○○|○○|○○</th>
  </tr>
  <tr>
    <th colspan=7 align="center">基础属性</th>
  </tr>
  <tr>
    <th>M</th>
    <th>ARM</th>
    <th>RC</th>
    <th>CC</th>
    <th>AW</th>
    <th>OR</th>
    <th>OS</th>
  </tr>
  <tr>
    <td>2</td>
    <td>2</td>
    <td>14</td>
    <td>8</td>
    <td>12</td>
    <td>4</td>
    <td>2</td>
  </tr>
  <tr>
    <th>ER</th>
    <th>ES</th>
    <th></th>
    <th></th>
    <th></th>
    <th>SO/LD</th>
    <th>Intel</th>
  </tr>
  <tr>
    <td>6</td>
    <td>4</td>
    <td></td>
    <td></td>
    <td></td>
    <td>8</td>
    <td>0</td>
  </tr>
  <tr>
    <th colspan=7 align="center">TA</th>
  </tr>
  <tr>
    <th>TL</th>
    <td>-2</td>
    <td>-1</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td colspan=1>4</td>
  </tr>
  <tr>
    <th>Cost</th>
    <td>2</td>
    <td>2</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td colspan=1>*</td>
  </tr>
  <tr>
    <th colspan=7 align="center">基础武器</th>
  </tr>
  <tr>
    <td rowspan=5>突击步枪</td>
    <th>攻击数</th>
    <th>数量</th>
    <th>穿甲</th>
    <th>击穿伤害</th>
    <th>后效伤害</th>
    <th>特殊规则</th>
  </tr>
  <tr>
    <td>2</td>
    <td>5</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>无</td>
  </tr>
  <tr>
    <th colspan=6 align="center">距离命中修正</th>
  </tr>
  <tr>
    <th>距离</th>
    <th>0</th>
    <th>1~4</th>
    <th>5</th>
    <th>6</th>
    <th></th>
  </tr>
  <tr>
    <td align="center">命中修正</td>
    <td align="center">-5</td>
    <td align="center">0</td>
    <td align="center">-1</td>
    <td align="center">-3</td>
    <td align="center"></td>
  </tr>
  <tr>
    <th colspan=7 align="center">特殊武器 SPS 1/5</th>
  </tr>
  <tr>
    <td rowspan=5>榴弹发射器</td>
    <th>攻击数</th>
    <th>数量</th>
    <th>穿甲</th>
    <th>击穿伤害</th>
    <th>后效伤害</th>
    <th>特殊规则</th>
  </tr>
  <tr>
    <td>1</td>
    <td>1</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>高爆（小）</td>
  </tr>
  <tr>
    <th colspan=6 align="center">距离命中修正</th>
  </tr>
  <tr>
    <th>距离</th>
    <th>0</th>
    <th>1~3</th>
    <th>4</th>
    <th></th>
    <th></th>
  </tr>
  <tr>
    <td align="center">命中修正</td>
    <td align="center">-5</td>
    <td align="center">+2</td>
    <td align="center">0</td>
    <td align="center"></td>
    <td align="center"></td>
  </tr>
  <tr>
    <th colspan=7 align="center">描述</th>
  </tr>
  <tr>
    <td colspan=7>
        战术人形小队由M4A1（基础12Pt）和4名战术人形（基础8Pt一人，32Pt）组成。<br>
        护具采用防弹插板（4Pt一人，20Pt），令ARM提升为2。<br>
    </td>
  </tr>
</table>

### 1.2 载具

将坐骑，车辆，飞行器等等可以搭载步兵的统称为载具。除了坐骑，载具是很难被彻底消灭的，但却可以用多种方法降低载具的作战能力。因此，结算载具所受损伤的方式与步兵有很大差距。

#### 1.2.1 击中部位判定

## 2 战斗流程

### 2.1 部署战场

战场由六边形格子组成。在条件受限的情况下，使用正方形格子的地图也是可行的。

一个格子大约是100米见方的空间，因此可以让很多单位堆叠在一个格子上。

### 2.2 整体流程

战斗由多个战斗轮组成。一个战斗轮中包含了所有在场单位各自的回合，以及在战斗轮最后的情报维持阶段。

* **单位回合** 根据单位的AW，以从高到低的顺序进行单位的回合。原则上一个单位在一个战斗轮中只有一个回合，并且在敌我双方存在AW相同的单位时，尽可能满足轮流行动的原则，也即是说，如果上一个回合是玩家A的回合，那么下一个回合尽可能是玩家B的回合。
* **情报维持** 当所有在场单位都执行完各自的回合时，来到了战斗轮最后的情报维持阶段。在情报维持阶段中，所有单位都可以执行一次免费的侦察行动（即名字中包含侦察二字的行动），侦察行动的目标必须是Intel至少为1的敌方单位。在情报维持阶段结束后，一个Intel至少为1的单位如果没有被成功的执行了侦察行动，那么该单位的Intel-1，否则保持不变。也就是说，在该阶段中需要通过成功的侦察行动来使敌方单位的Intel不降低。
* 在一些情况中，单位的AW会发生变化，使得还没进行回合的单位的AW高于当前正在进行回合的单位，或已经进行回合的单位的AW低于当前正在进行回合的单位。根据两个原则进行判定：按AW从高到低进行回合；一个战斗轮中只有一个回合。因此，前者会在当前回合结束后进行回合，后者不会因为AW降低而进行第二个回合。通过将所有还没执行回合的单位按AW从高到低的顺序，来决定接下来的进行回合顺序。

### 2.3 回合流程

### 伤害结算

伤害结算分为三个阶段，命中判定，击穿判定 计算伤害。

* 根据总射击数掷骰，得出命中数。
* 对于每个命中roll击穿判定，结果为武器穿甲+d6。结果大于目标的护甲，则击穿：结果大于护甲+4，则过穿。
* 如果击穿，则对目标施加击穿伤害。如果击穿且未过穿，则额外施加后效伤害。
* 单次命中只能击杀一个步兵。  

## 非战斗环节

如果将该规则扩展为跑团的话，

## 范例卡

<table>
  <tr>
    <th colspan=8 align="center">大头步兵班</th>
  </tr>
  <tr>
    <th>HP</th>
    <td>1</td>
    <th>人数</th>
    <td>5</td>
    <th>总HP</th>
    <td>1x5=5</td>
    <th>移动力</th>
    <td>2</td>
  </tr>
  <tr>
    <th>护甲</th>
    <td>2</td>
    <th>单人分值</th>
    <td>5</td>
    <th></th>
    <td></td>
    <th></th>
    <td></td>
  </tr>
  <tr>
    <th colspan=8 align="center">地形适应性</th>
  </tr>
  <tr>
    <th>地形等级</th>
    <td>-2</td>
    <td>-1</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td colspan=2>4</td>
  </tr>
  <tr>
    <th>移动消耗</th>
    <td>2</td>
    <td>2</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td colspan=2>*</td>
  </tr>
  <tr>
    <th colspan=8 align="center">基础武器</th>
  </tr>
  <tr>
    <th>武器名称</th>
    <th>射击数</th>
    <th>射程</th>
    <th>穿甲</th>
    <th>击穿伤害</th>
    <th>后效伤害</th>
    <th>特殊</th>
    <th>分值</th>
  </tr>
  <tr>
    <td>突击步枪</td>
    <td>2</td>
    <td>6</td>
    <td>0</td>
    <td>1</td>
    <td>0</td>
    <td>无</td>
    <td>1</td>
  </tr>
  <tr>
    <td>反坦克步枪</td>
    <td>1</td>
    <td>8</td>
    <td>2</td>
    <td>1</td>
    <td>1</td>
    <td>无</td>
    <td>2</td>
  </tr>
</table>


<table>
  <tr>
    <th colspan=8 align="center">动力甲步兵班</th>
  </tr>
  <tr>
    <th>HP</th>
    <td>2</td>
    <th>人数</th>
    <td>3</td>
    <th>总HP</th>
    <td>2x3=6</td>
    <th>移动力</th>
    <td>2</td>
  </tr>
  <tr>
    <th>护甲</th>
    <td>4</td>
    <th>单人分值</th>
    <td>10</td>
    <th></th>
    <td></td>
    <th></th>
    <td></td>
  </tr>
  <tr>
    <th colspan=8 align="center">地形适应性</th>
  </tr>
  <tr>
    <th>地形等级</th>
    <td>-2</td>
    <td>-1</td>
    <td>1</td>
    <td>2</td>
    <td>3</td>
    <td colspan=2>4</td>
  </tr>
  <tr>
    <th>移动消耗</th>
    <td>2</td>
    <td>2</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td colspan=2>*</td>
  </tr>
  <tr>
    <th colspan=8 align="center">基础武器</th>
  </tr>
  <tr>
    <th>武器名称</th>
    <th>射击数</th>
    <th>射程</th>
    <th>穿甲</th>
    <th>击穿伤害</th>
    <th>后效伤害</th>
    <th>特殊</th>
    <th>分值</th>
  </tr>
  <tr>
    <td>榴弹步枪</td>
    <td>2</td>
    <td>6</td>
    <td>0</td>
    <td>1</td>
    <td>1</td>
    <td>无</td>
    <td>3</td>
  </tr>
</table>
