# Advanced: Special Symbols

NovelAI의 데이터셋에는 이야기의 특정 부분을 표시하기 위해 일부 **symbols**이 일관적으로 사용되었습니다. 텍스트 생성을 위한 프롬프팅을 할 때 이런 **tokens**를 직접 사용하면 특정 데이터의 분류를 끌어올 수 있습니다.


## `>` Arrowing

"~를 초과하는"이라는 사인인 `>`을 문장 앞에 ***right-pointing arrow***로 사용하는 것은 문맥에 따라 다양한 용도로 사용됩니다.

가장 일반적인 용법은 [Text Adventure](./text_adventure.md) 플레이어의 명령입니다만, 일반적인 **text messages**, **email quotes**, **computer output**에도 사용할 수 있습니다. 보통 텍스트 앞에 공백을 둡니다.


## `*`Asterisking`*`

애스터리크로 둘러쌓인 텍스느는 `*bang*`이나 `*Kaboom!*`와 같은 소리 효과나 `*ahem`이나 `*sigh*`처럼 특정한 발성을 신호화하여 나타냅니다.

`"Oh you know I just *love* chocolate milk."`와 같이 말의 특정 부분을 강조할 때도 쓰일 수 있습니다.


## `<`Chevronning`>`

일반적인 `"`따옴표`"` 대신, 꺽쇠 괄호로 알려진 **chevrons**로 `<`보다 작고, 보다 큼`>`을 사용하면 텔레파시 혹은 수화나 글*writing* 같은 비음성적 대화에 태그를 지정할 수 있습니다.

 예를 들어: `<Be not afraid,> the creature's inner voice resonated inside my mind.`


## `***` Dinkusing

재미있는 이름을 한 `***` **dinkus**는 *장면*이나 *챕터를 나누는*데 사용됩니다.

스토리에 `***`만 있는 줄을 작성하면 사용자는 다음에 오는 내용을 건너뛰고 싶다는 것을 AI에게 이해시킬 수 있습니다.


## `⁂` Asterisming

Dinkus의 큰 형님인 `⁂` **asterism**은 완전히 새로운 이야기로의 전환을 가리키는데 사용됩니다.

다음 줄에서 완전히 다른 캐릭터와 플롯으로 다른 이야기의 시작이 되길 원하는 경우에만 `⁂`을 한줄에 단독으로 사용하세요. 단편 모음집에서 유용합니다.

*NovelAI의 텍스트 편집기에서 **마우스 오른쪽 버튼 클릭 메뉴**를 통해 이 문자에 쉽게 접근할 수 있습니다.*


## { Curly Bracing } *Instructions*

중괄호 사이에 빈 공백과 텍스트가 채워진 **{ 중괄호 }** 는 AI에게 **직접적인 지시**를 내리는데 사용됩니다.

[Special Modules](./advanced_special_modules.md#instruct) 페이지에서 광범위하게 다뤄집니다.


## [ Spaced Bracketing ]

대괄호 사이에 빈 공백과 텍스트가 채워진 **[ 대괄호 ]** 는 다양한 케이스에서 사용될 수 있습니다..

1. **ATTG**: [ **A**uthor: ; **T**itle: ; **T**ags: ; **G**enre: ]<p>
스토리에 대한 선택적인 초기자로 사용될 수 있습니다. **ATTG**는 새로운 이야기와 강하게 관련이 되어있으므로, AI가 장기기억 문제를 겪지 않게 하려면 가장 위에 이것을 두십시오. **Memory**의 첫번째 행이 좋은 위치입니다. *Author*와 *Title*은 유용도가 가장 떨어지므로 원하지 않는다면 생략할 수 있습니다. <p>
Example: `[ Tags: London, 1820s, dragons; Genre: steampunk, drama ]`<p>
(고유명사는 대문자로, 나머지는 소문자로)

1. **장면**을 전환하거나 설정<p>
`[ London, 1821 ]`, `[ Woodstock, 1969, 22:30 ]`, `[ New York, 1935, Night Club ]`, `[ Monday, 8:00 A.M. ]`, `[ Five Minutes Later ]` 등. 이것은 *Author's Note*를 포함한 아무 곳에서 사용할 수 있습니다.


1. 캐릭터 간의 **시점**을 전환<p>
`[ John ]`, `[ Batman ]` 등. AI가 이름으로 인식하지 않으면 작동하지 않을 겁니다. Memory에 사용하여 AI가 주인공을 추적하는데 도움을 줄 수도 있습니다.


1. **스타일** 태그 (**Krake**, **Clio**와 **Kayra** 전용)<p>
Examples: `[ Style: essay, nonfiction ]`, `[ Style: verbose ]`, `[ Style: poetry ]`,` [ Style: text adventure ]`, `[ Style: chat ]`, 심지어 `[ Style: SFW ]` 등의 스타일 태그를 지정하면 AI가 **더욱 더** 스타일을 깔끔한 상태를 유지하는데 도움이 됩니다.<p>
이것은 작가노트에 넣어도 스토리 진행을 방해하지 않습니다.


1. **지식** 태그 (**Clio**와 **Kayra** 전용)<p>
`[ Knowledge: paradoxes ]`, `[ Knowledge: anime in 90s ]`. 이것은 모델이 표시된 주제에 대한 이야기를 하도록 유도합니다. 위의 스타일 태그와 결합하여 다양한 효과를 낼 수 있습니다.<p>
Examples: `[ Knowledge: CRPGs; Style: blog post ]`, `[ Knowledge: supernatural; Style: podcast, transcript ]` 등.


1. *일반 컨텍스트*와 *작가노트/메모리/로어북*을 **구분**<p>
때떄로 AI이 숨겨진 컨텍스트의 내용을 그대로 *복사*하는 경우가 있는데, 이를 이처럼 공백있는 대괄호로 묶어두면 이를 피하는데 도움이 될 수 있습니다. **Clio**와 **Kayra**와 같은 최신 모델에서는 이런 일이 잘 발생하지 않으므로 이것이 필용하지 않을 수도 있습니다.


1. `[ An Unexpected Quest ]`, `[ The End of Many Things ]`, `[ Into the Wastes ]`, `[ Time Loop (3rd Restart) ]` 등과 같이 ***챕터의 제목***으로 사용할 수도 있습니다. 비록 그 결과는 예측할 수 없지만요.<p>
`[ Prologue ]`나 `[ Epilogue ]`는 다소 일관된 효과를 보인다는 점은 주목할만 합니다.<p>
*dinkus 다음에 나올 때 가장 잘 작동해야 합니다.*

Note: 이러한 용도의 경우, 대괄호는 **항상** 텍스트의 시작과 끝을 공백으로 채워야 합니다. 간격을 두지 않은 대괄호는 **주석**이나 **설명** 등에서 주로 사용되는 용도입니다.

> ![](./goose.png) **Goose tip:**
다른 사용법으로 자유롭게 실험해보세요. 하지만 플라시보 효과를 주의해야해요. 위 용도를 제외하면 괄호를 제거하는 것이 더 좋은 결과를 얻을 수도 있어요.


## ---- Horizontal Lining

한 줄에 `----` 이렇게 "네개의 하이픈"만 있으면 일반 스토리텔링이 아니라 정보를 제공하는 텍스트임을 가리킨다.

예를 들어, 다음과 같은 정보를 덤프하는데 사용할 수 있다
```
----
Elves are very proud.
They have pointy ears.
***
```

그리고나서 `***` dinkus와 함께 보통의 산문 스토리텔링을 다시 시작할 수 있고, 다른 정보 항목을 작성하고 싶은 경우에는 **다른 수평 라인** `----`을 다시 사용할 수도 있다.

예를 들어 다음과 같이  **수평 줄** 바로 뒷 줄에 정보의 카테고리를 단독으로 작성하여 범주를 가리키는데 사용할 수도 있다:

```
----
Characters:
Sigurd, a strong warrior who wields a mighty sword.
Euterpe, a skilled bard who plays a tooty horn.
Goose, a handsome scholar full of valuable advice.
----
Glossary:
Infinibag: A magic pouch that can contain infinite items as long as they fit.
Xenoarchaeologist: A scientist that studies ancient relics of alien origins. 
Peach Festival: A peach-themed festival that celebrates a bountiful harvest.
***
```

카테고리에 `?`를 추가하여 AI가 틀리기 쉬운 것에 대해 "추가적인 정보를 제공"할 수도 있습니다. 예시:

```
----
Snake
Type: animal, reptile
Legs?: None (squamous land tetrapods are legless)
***

```


> ![](./goose.png) **Goose tip:**
항상 ----를 포함하도록 컨텍스트 설정의 접두사 및/또는 접미사를 변경할 수 있어요. ***은 정보 항목에서 일반 스토리텔링으로 이동할 때만 사용해야 한다는 것을 기억하세요.

> ![](./goose.png) **Goose tip:**
문맥에 ----가 너무 많다면 AI는 ---- 자체를 출력으로 뱉기 시작할 수도 있어요. 그것을 막고 싶다면 해당 토큰에 대해 bias를 사용하거나 밴하는 것을 추천해요.


## ====== Horizontal Barring

**Clio**와 **Kayra** 전용으로, 6개의 등호로 이루어진 **수평 막대** `======`는 포럼의 게시글 구분자처럼 사용되는데 아래에 **유저명**을 입력하여 게시자를 가리키고 그 위에 **스레드**의 이름(선택 사항)을 입력할 수 있습니다.

```
Thread: Let's chat about AI!
======
Kurumuz
```

수평 막대는 이메일의 구분자로도 사용될 수 있습니다.

## Wide spacing

데이터셋의 일부 위치에 *"보통보다 넓은"* 두개의 공백 문자 타입이 사용되었습니다. 필요하다면 NovelAI 에디터에서 마우스 오른쪽 버튼 메뉴를 띄워 쉽게 둘 다 입력할 수 있습니다.

### En Spacing

(` `) En Space는 따옴표, 문자, 기호 등 텍스트 안의 다양한 상황에서 사용됩니다.


### Em Spacing

(` `) Em Space는 시나 음악의 가사에서 사용됩니다.


> ![](./goose.png) **Goose tip:**
해당 띄어쓰기가 어떤 띄어쓰기인지 기억하기 쉬운 방법은 문자 `n`이 문자 `m`보다 더 얇은 글자이기 때문에 en spacing이 더 얇은 공백이고, em spacing이 더 넓은 공백이라고 기억하는 거에요.


## `─` LitRPGing

`─` 문자는 기술적으로 *"Box Drawings Light Horizontal"* 이라고 불리지만 일반적으로는 **"LitRPG Line"** 이라고 불립니다. `─` 문자는 줄의 시작 부분에서 캐릭터의 스탯이나 속성, 소유하고 있는 것들 등, 일부 LitRPG 관련 텍스트를 표시할 때 사용됩니다.

```
─ You gained a level in Dragoon! You earned the Class Perk: Dragon Slayer!
─ Dragon Slayer: your attacks deal bonus damage on reptile and aquatic targets.
```

*NovelAI의 텍스트 에디터에서 **마우스 오른쪽 버튼의 메뉴**를 통해 쉽게 이 문자를 입력할 수 있습니다.*

## Noting: *Experimental*

**Clio**와 **Kayra**에서만 다음과 같이 작성하여

```
Notes:
- 
```

이를 컨텍스트 하단의 새로운 줄에 입력하면 AI에게 앞의 텍스트와 관련된 *주석 스타일의 주석*와 *관찰 내용*을 생성하도록 유도할 수 있습니다.

상당히 비일관적이고 랜덤하게 뭔가를 만들어내는 경향이 있자만 재미로는 사용해볼 수 있습니다.

이것을 사용하는 것 대신에 [Instruct Module](./advanced_special_modules.md#instruct)을 사용하여 사용자가 원하는 것에 대한 적절한 노트를 요청하는 것을 추천합니다.

## `##` Commenting out

이것은 엄밀히 말하면 데이터셋에서 특정 이유로 사용되는 **기호**는 아닙니다만, **에디터의 텍스트 영역** 자체에서 제공하는 기능의 문자열입니다.

줄 제일 처음에 `##`를 사용하면 AI의 컨텍스트로부터 해당 줄을 주석처리를 할 수 있습니다.

예를 들어, 다음과 같은 글이 있다고 해봅시다

```
Dwarves are very proud.
##just like the elves lol
They have large beards.
```

**에디터**에서 위처럼 작성했지만, AI는 글 전체가 아니라 아래와 같은 글을 "볼" 것입니다.

```
Dwarves are very proud.
They have large beards.
```

`##`은 다른 사람을 위해 만든 **시나리오**에 코멘트를 작성하거나 이야기 중간에 메모를 남기는데 유용할 것입니다.

***주석처리**를 하기 위해서는 ##이 해당 줄의 처음에 위치해야 한다는 사실을 기억하십시오. 그러므로 여러 줄을 **주석처리**하기 위해서는 각 줄의 시작부분에 ##를 입력해야 합니다.*
*원한다면 ## 뒤에 공백을 둘 수 있습디만 기능적으로는 차이가 없습니다.*