# 大概是美少女兵棋

（初步设想：侦察，攻击，共享情报）

## 战斗单位

地图上，最基本的作战单元是单位（Unit）。一个单位由一个或多个的步兵或载具构成，它们以单位为整体进行行动。步兵与载具的差距非常大，下面分开进行描述。

### 步兵

步兵是战斗的核心，即使是载具，也需要步兵作为乘员进行操纵。当一方丧失了所有的步兵（含载具的乘员）时，认为是被彻底歼灭，失败。

#### 基本属性

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

#### 其他属性

Action Point，AP：行动点，用于主动回合中执行行动。在单位的回合开始时，除非有特殊说明，AP回复到2。

Reaction Point，RP：反应点，用于非主动回合中执行反应。在单位的回合开始时，除非有特殊说明，RP回复到1。

Special Weapon Slots，SPS：特武槽位，决定了最大能携带多少特武。

Tactical Accessory Slots，TAS：战术道具槽位，决定了最大能携带多少战术道具。

#### 选择武器

一个步兵必须从她可以选择的普通武器中选择至少一项。一般而言，一个步兵只能有一项普通武器，但近战武器除外，在对战双方同意的情况下也可以选择多项普通武器。但是，无论具有多少普通武器，在一次射击/近战行动中，一个步兵只能使用其中的一项进行攻击。

此外，她还可以从能选择的特殊武器中进行选取，详细规定见组成单位一节。

#### 选择护甲

护甲不是必选项，但一般而言步兵都装备了护甲。护甲主要提高了步兵的ARM，令各类武器在命中时更难击穿，从而提高步兵的存活能力。

#### 选择战术道具

战术道具不是必选项，但战术道具可以提高步兵应对各种情况的能力。

#### 组成单位

多个步兵组成一个单位，作为一个整体进行行动。一般而言，单位中的步兵的各项属性应当一致，从而更方便进行结算。在少数不一致的情况下，单位作为一个整体，基本属性的调整原则为：

* M，ARM取各步兵中的最低值。
* AW，OR，OS，ER，ES，TA取各步兵中的最高值。
* HP，RC，CC依旧保留。也就是说，在结算攻击命中时，各步兵用他们自己的RC/CC作为判定根据。在结算步兵阵亡时，不同步兵的HP也分别结算。

当单位中存在属性不一致的步兵时，随着单位承受伤亡，属性也可能发生相应变化。因此推荐用属性一直的步兵组成单位。

此外，单位具有两项属性：SPS和TAS。单位中每存在一个步兵，就获得1SPS和2TAS。因此当单位承受伤亡，SPS和TAS也随之下降。如果单位携带的特殊武器或战术道具超过了SPS和TAS的限制，那么就必须丢弃掉一部分，从而满足限制。控制承受伤亡单位的玩家选择丢弃掉哪些特殊武器或战术道具。

举例：由3名改造人类组成的单位装备3把电浆步枪，总点数为3，SPS也刚好为3，满足限制。在随后战斗中，一名改造人类阵亡，SPS随之降低为2，必须将特殊武器总点数降低到2以下，因此丢弃1把电浆步枪。

## 战斗流程

### 伤害结算

伤害结算分为三个阶段，命中判定，击穿判定 计算伤害。

* 根据总射击数掷骰，得出命中数。
* 对于每个命中roll击穿判定，结果为武器穿甲+d6。结果大于目标的护甲，则击穿：结果大于护甲+4，则过穿。
* 如果击穿，则对目标施加击穿伤害。如果击穿且未过穿，则额外施加后效伤害。
* 单次命中只能击杀一个步兵。  

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
