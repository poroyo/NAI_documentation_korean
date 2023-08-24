# Slider Settings

<img src="./SlidersTab.gif" style="float: right; height: 800px; width: 40%; margin: 10px;">

- [Config Preset](#config-preset)
- [Generation Options](#generation-options)
    - [Randomness](#randomness)
    - [Output Length](#output-length)
    - [Repetition Penalty](#repetition-penalty)
- [Sampling](#sampling)
    - [CFG Scale](#cfg-scale)
    - [Mirostat](#mirostat)
    - [Nucleus](#nucleus)
    - [Tail Free](#tail-free)
    - [Top A](#top-a)
    - [Top K](#top-k)
    - [Top G](#top-g)
    - [Typical](#typical)
    - [Sampling Order](#change-settings-order)
- [Repetition Penalty](#repetition-penalty-1)
- [Alternative Repetition Penalty](#alternative-repetition-penalty)


## Config Preset

<img src="./SliderPresetsDropdown.png" style="width: 300px; max-width=100%">

상단의 **Config Preset** 드롭다운 메뉴는 사용자가 저장하거나 임포트한 모든 프리셋들이 표시되며, 그 아래에 NovelAI의 기본 프리셋들이 나열됩니다. 각 모델은 모델들이 가진 다양한 기본 프리셋이 딸려있으며 이들은 주로 창의적인 글쓰기를, 일부는 특정 글쓰기나 생성 스타일을 위해서 튜닝되었습니다. 드롭다운 메뉴 옆의 펜 아이콘은 선택한 프리셋의 이름을 변경하기 위한 것입니다.

**Import** 및 **Export** 버튼은 여러분의 프리셋을 공유하거나 다른 사람이 공유한 프리셋을 가져올 때 사용될 수 있으며 아래 세팅 중에 하나를 수정할 때마다 **Update active Preset** 팝업이 드롭다운 아래에 나타납니다. **Update active Preset** 드롭다운에서 현재 프리셋을 저장하고, **Reset Changes**를 통해 프리셋을 원래 설정으로 되돌리거나 새 프리셋에 현재 변경점을 저장할 수 있습니다!

## Generation Options

<p align="center"><img src="./GenerationOptions.png" width="350"></p>

이 페이지의 **Generation Options** 섹션은 세가지의 기본 생성 세팅을 포함하고 있습니다: **Randomness**, **Output Length** 그리고 **Repetition Penalty**. 이 세팅들은 대부분 아래의 [Sampler](#sampling)의 어느 것도 조절할 필요 없이 그때그때 봐가면서 조절하기 명확하고 쉬운 것들 입니다.

### **Randomness**<p>
가장 단순하게, **Randomness** 값은 생성되는 다른 토큰들의 확률이 얼마나 *균등*한지를 결정하며, 토큰 확률 간의 *차이*를 늘리거나 줄이지만 *결코* 토큰들의 초기 순서는 재배열하지 않습니다.</p><p>
값이 1보다 **크다면**, 낮은 확률의 토큰은 **더 높은 확률**의 토큰에 가까워지도록 기회*chance*가 **증가**합니다. 값이 1보다 **작다면**, **더 높은 확률**의 토큰은 **더 낮은 확률**의 토큰에서 더 멀어지도록 기회*chance*가 증가합니다.</p><p align="center"><img src="./Samplersample1.png"></p>
예를 들어, 만약 위 이미지를 프롬프트로 사용하고 생성될 토큰의 [확률](./editor.md#token-probabilities)을 보면...

<p align="center">
<table style="border: 1px solid">
<tr>
<td>
<img src="./randomness1.png" width="300">
</td>
<td>
<img src="./randomness125.png" width="300">
</td>
</tr>
<tr>
<td>
Randomness 1.0 
</td>
<td>
Randomness 1.25 
</td>
</tr>
</table>
</p>
</p>

**상위** 토큰의 **after** 확률이 상당히 **낮아**진 것을 볼 수 있는 반면, 그 다음에 이어지는 토큰들은 그렇게 심하게 떨어지지 않을 것을 볼 수 있습니다. 해당 수치를 높임으로써 상위 토큰들이 전보다 낮은 확률을 갖게 됨에도 불구하고, 낮은 확률의 토큰에게 더 커진 생성 기회를 주게 됩니다.

### **Output Length**<p>
**Output Length**는 AI가 출력당 생성할 수 있는 텍스트 문자의 최대량을 조절합니다. 최소 4자에서 최대 600자까지입니다. AI 생성의 특성 때문에 긴 출력길이는 품질이 달라질 수 있으니 주의해야 하며, 짧은 출력 길이가 주제를 더 잘 유지하는 경향이 있습니다.
</p>

### **Repetition Penalty**<p>
**Repetition Penalty** 슬라이더는 **context**에서 토큰이 나타날 **확률**에 패널티를 적용하며, 여러번 나타나는 것에는 더 심한 패널티를 부과합니다. 해당 값이 높다면 더욱 심한 패널티를 적용하므로 이 슬라이더를 너무 높이면 출력이 저하되거나 다른 의도치않은 동작을 발생할 수 있습니다. 반면에 너무 낮은 세팅 값에서는 AI가 계속 같은 단어나 구두점을 반복할 수 있습니다. 해당 세팅을 살짝 조절하여 스토리의 페이스나 포커스에 대해 안내하는데 도움이 될 수도 있습니다. 예를 들어, 만약 AI가 특정 캐릭터의 이름이나 세부 사항을 더욱 자주 언급하게 하고 싶다면 해당 슬라이더를 낮추고, 더 다양한 단어 선택을 사용하게 하고 싶다면 이 슬라이더를 높이십시오.
</p>


## Sampling

<p align="center"><img src="./Sampling.png" width="350"></p>

아래의 샘플링 옵션은 생성될 때 토큰이 어떻게 재분배되는지, 어떻게 트리밍*trimming*되는지를 변경합니다.

### CFG Scale

[Advanced: CFG Scale](./advanced_cfg.md)를 참조하십시오.

### Mirostat

**Mirostat**에는 **Tau**와 **Learning Rate**라는 두개의 슬라이더가 있습니다. 이 샘플러는 Tau 값으로 지정된 주어진 복잡도로 텍스트를 유지하려고 시도하며, 세팅이 높을수록 더욱 복잡한 텍스트를 제공하려고 시도합니다. Learning Rate 슬라이더는 샘플러가 컨텍스트에 얼마나 빠르게 적응할지를 지정합니다. 1로 설정하면 즉각적이고, 낮은 세팅일수록 완화됩니다. 이 샘플러와 [Settings Order](#change-settings-order)의 다른 샘플러와 함께 사용하는 것은 권장되지 않습니다.

### Nucleus

**Nucleus** 샘플링은 **Top-P**라고도 하며, **가장 높은** 확률의 토큰을 선택하고 각각의 후속 토큰들의 확률의 합이 설정한 **Nucleus** 값에 도달할 때까지 후속 토큰들의 확률을 더합니다. 나머지 토큰들은 모두 **잘려서** 출력의 일관성은 높아지지만, 이 과정에서 많은 **낮은** 확률의 토큰들이 **사라지게**되어 창의성이 희생됩니다. 해당 슬라이더를 **낮게** 설정할 경우 더 많은 토큰이 사라지므로, 해당 값을 실험할 때는 조금만 조정하는 것을 추천합니다.


### Tail Free

**Top K**와 **Nucleus** 샘플링을 대체하기 위해 고안된 **Tail Free**은 출력의 확률의 '꼬리'를 계산하기 위해 수학 공식을 사용합니다. 꼬리, 그리고 **Tail Free** 샘플러에 대한 자세한 설명은 [이](https://www.trentonbricken.com/Tail-Free-Sampling/) 블로그 게시글에서 자세히 설명되어 있습니다. 이 샘플러는 가장 낮은 확률의 임계점을 출력 확률 분포의 '**꼬리**'로 결정한 다음 이를 제거합니다. 이렇게 제거된 후에 살아남은 토큰들은 보상을 위해 확률을 재조정합니다.

간단하게 말해, 이 세팅은 출력의 [Logical Probabilities](./editor.md#token-probabilities) 하단에서 수식*formula*이 최악의 가능성의 토큰으로 간주한 것의 일부를 잘라내는데 도움을 줍니다. 이 슬라이더를 조절할 때는 조금만 조정하는 것을 추천합니다. **Tail-Free**를 0에 가깝게 설정할수록 **최악**의 토큰으로 간주되는 임계점이 더 커지고 강해지기 때문입니다.

### Top A

**Top-A** 샘플링에서 설정한 값은, 허용되는 **가장 낮은** 토큰 확률을 자르는 기준점을 정의합니다. Top A 값이 **높을수록** 더 엄격해져 더 많은 토큰을 잘라내는 반면, Top A를 **낮게** 설정하면 더 적은 토큰을 잘라냅니다. 이 제한은 **가장 높은** 확률 토큰을 기준으로 조정됩니다. 예를 들어 한 토큰의 집합에서 상위 토큰이 낮은 확률을 갖는다면, **Top-A** 값이 같을지라도 상위 토큰이 **더 높은** 확률을 가진 집합의 경우보다 잘라내는 토큰의 제한은 **더 낮게** 조정됩니다.

### Top K

**Top K**는 사용과 조정이 가장 간단한 샘플러입니다. **Top K**가 적용되면, 생성되는 토큰의 풀이 슬라이더 설정에 맞게 제한됩니다. 예를 들어, **Top K**가 10으로 설정되어 있다면, 이 샘플러는 최상위 10개의 토큰을 제외한 모든 토큰을 제거합니다. 이 샘플러의 단점은 풀에 있는 토큰의 수가 처음에 설정한 **Top K** 세팅보다 적으면 이 샘플러는 아무런 효과가 없다는 것입니다.

> ![](./goose.png) **Goose tip:**
**Top K**을 1로 설정하면 생성을 다시 시도할 때마다 **같은** 토큰을 얻게 되요!

### Top G

**Top G**는 **Top K**와 비슷하게 기능하지만, 가능한 토큰의 최대 수를 제한하는 대신 토큰 **그룹**의 최대 수를 제한하는 설정을 합니다. 여기서 그룹이란 **같은** 확률 값을 공유하는 토큰의 집합을 말합니다. 이 기능은 Kayra 모델에서만 지원합니다.


### Typical

**Typical** 샘플링은 약간 더 복잡한 옵션 중에 하나입니다. 각각 생성된 출력 토큰에 대해 **conditional entropy**라는 것을 계산하는데, 이는 예상되는 **다음** 토큰의 **information content**의 척도입니다. 계산된 값이 **Typical** 세팅과 같거나 **더 높을** 경우, 혹은 **Typical** 세팅의 **음수** 값보다 **낮으면** 토큰이 잘립니다.


### Change Settings Order

<p align="center"><img src="./OrderSettings.png"></p>

**Order Settings** 창을 통해 **샘플러**의 순서를 바꿀 수 있습니다. 샘플러는 위에서부터 아래로 적용됩니다. 화살표 버튼을 사용하거나 개별 박스를 드래그하여 샘플러 순서를 바꾸고 오른쪽의 버튼을 눌러 토글하십시오. Temperature(Randomness)는 비활성화**할 수 없습니다.**

샘플러는 적용하는 순서는 예상할 수 없는 효과를 일으킬 수 있으므로 기본 구성 프리셋으로 시작하여 실험을 해보십시오.


## Repetition Penalty

<p align="center"><img src="./RepetitionPenalty.png" width="300"></p>

**Repetition** 섹션과 아래의 [Alternative Repetition Penalty](#alternative-repetition-penalty) 옵션들은 모두 글 생성을 덜 반복적으로 만들기 위한 것입니다.

- **Phrase Repetition Penalty**<p>
더 자세한 설명을 위해 [Advanced: Phrase Repetition Penalty](./advanced_phrase_repetition_penalty.md)을 참조하십시오.
</p>

- **Use Default Whitelist**<p>
화이트리스트 토큰의 전체 리스트를 보려면 [Repetition Penalty Whitelist](https://docs.novelai.net/text/reppenwhitelist.html)를 참조하십시오.
</p>

- **Range**<p>
**Repetition Penalty Range**는 **Story Context**의 아래부터 시작해서 몇 개의 토큰에 **Repetition Penalty** 설정이 적용될 것인지를 나타냅니다. 이 값을 최소치인 0(off)로 설정하면, 반복 패널티는 출력 전체에 걸쳐 적용되며, 이는 슬라이더를 **Subscription Tier**의 최대로 설정한 것과 같습니다. 이 슬라이더는 **Dynamic Range**가 비활성화된 경우에만 작동합니다.
</p>

- **Slope**<p>
**Slope** 슬라이더는 컨텍스트의 가장 최근 토큰과의 거리에 따라, 설정한 **Repetition Penalties**(**Phrase Repetition Penalty**는 **제외**)의 몇퍼센트를 컨텍스트의 토큰에 적용할 지를 지정합니다. 비활성화되면 기울기가 적용되지 않으며 모든 패널티가 평범하게 적용됩니다.<p>
**Slope**가 1과 **같거나** 1보다 **작은** 값으로 설정된다면, **마지막** 토큰만 100%의 패널티 값을 받고, 이전 토큰들은 **줄어든** 패널티 퍼센트를 겪게 됩니다. 이 감소는 **Slope**를 0에 가깝게 설정할 수록 완만하고 점진적이 됩니다. 값을 정확하게 1로 설정하면, 각 토큰에 대한 퍼센트 감소는 **동일**한 양이 되고 기울기가 곧은 상향선이 됩니다.<p>
만약 값이 1보다 **크다면**, **Slope**는 직선에서 계단 모양으로 바뀌고, **Slope** 값이 최대값인 10에 가까워질수록 *더* 강렬*intense*해집니다. 이 범위에서, 가장 최근의 여러 토큰이 100%의 패널티 값을 받을 수 있지만, 이전 토큰은 갑자기 패널티 비율이 크게 감소하는 "절벽"이 형성됩니다. **Slope**가 10이면, 컨텍스트의 절반은 100%의 패널티 값을 받는 반면, 나머지 절반은 패널티를 전혀 받지 않습니다.
</p></p></p>

- **Dynamic Range**<p>
해당 값이 활성화되면 **Dynamic Range** 토글은 **Repetition Penalty** 설정을 **Story** 텍스트에만 적용되도록 만듭니다. 즉, **Memory**, **Author's Note**, **Lorebook** 텍스트 내에는 적용되지 않음을 의미합니다. 이것을 활성화하면 AI는 해당 세션에서 언급된 설명 등을 더 자주 언급할 수 있으며 **Range** 슬라이더가 조절되는 것을 방지할 수 있습니다.
</p>


## Alternative Repetition Penalty

<p align="center"><img src="./AlternativeRepPen.png" width="300"></p>

**Alternative Repetition Penalty** 섹션의 이 설정은 매우 고급 기능입니다. 아주 약간 슬라이더를 조절해도 AI에 커다란 영향을 줄 수 있으며, 너무 많은 토큰을 잘라내어 자주 헛소리하는 결과가 나올 것입니다. 이 값을 실험할 때는 매우 작은 조정만을 사용하고, **범위** 설정을 조심하십시오.

- **Presence**<p>
**Presence** 패널티는 기본 **Repetition Penalty**와 비슷하게 동작하지만, 토큰이 얼마나 자주 나타나는지 조정하는 대신 토큰이 나타날 때마다 일정한*flat* 패널티를 적용합니다. **Presence** 패널티를 실험할 때는 매우 작은 조정만을 하는 걸 추천하는데, 이 값을 너무 높게 설정할 경우 구두점 토큰이 빠르게 패널티를 받아 생성되지 않을 수 있습니다.</p>

- **Frequency**<p>
**Frequency** 패널티는 얼마나 자주 토큰이 나타나는지에 따라 적용되며, 더 일반적인 토큰에는 패널티를 부과하고 덜 일반적인 토큰에는 덜 부과합니다. 만약 이 값이 너무 높다면, **Frequency**는 빠르게 출력의 품질을 저하시킬 수 있으므로, 이것을 실험할 때는 매우 작은 조정만을 해야 합니다. </p>