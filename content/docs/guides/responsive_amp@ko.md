---
$title: Style & Layout
---
[TOC]

AMP HTML 페이지의 스타일과 레이아웃은 일반 HTML 페이지와 매우 유사합니다. 두 가지 경우 모두 CSS 를 사용합니다.

 하지만 AMP 는 성능 및 사용성을 위해 일부 CSS의 사용이 제한됩니다. 대신 [자리표시자 및 대체](/ko/docs/guides/responsive/placeholders.html)
, [srcset을 통한 고급 아트 디렉션](/ko/docs/guides/responsive/art_direction.html) , [레이아웃 속성](/ko/docs/guides/responsive/control_layout.html) 과 같은 기능으로 반응형 디자인 기능을 확장하여 요소 표시 방법을 더 효과적으로 관리할 수 있습니다.

{% call callout('도움말', type='success') %}
 AMP 에서 요소를 반응형으로 만드는 것은 아주 쉽습니다. `layout="responsive"` 만 추가하면 됩니다. AMP 의 반응형 디자인을 자세히 알아보려면 [반응형 AMP 페이지 만들기](/ko/docs/guides/responsive/responsive_design) 를 참조하세요.
{% endcall %}

{{ youtube('y6kA3u3GIws', 480, 270, caption='AMP를 처음 사용할 때 어려운 점을 비롯하여 새롭게 설계된 AMP 프로젝트 사이트에 관한 UpperQuad의 이야기를 들어보세요.') }}

## 페이지에 스타일 추가

 문서 헤드에서 `<style amp-custom>` 태그 내에 모든 CSS 를 추가합니다. 예:

[sourcecode:html]
<!doctype html>
<head>
  ...
    <style amp-custom>
      /* any custom styles go here. */
      body {
        background-color: white;
      }
        amp-img {border: 5px solid black;
      }
    amp-img.grey-placeholder {
    background-color: grey;
    }
    </style>
    ...
</head>
[/sourcecode]

{% call callout('중요', type='caution') %}
 AMP 에는 `<style amp-custom>` 
태그가 하나 이상 허용되지 않으므로 페이지에 태그가 하나만 있어야 합니다.
{% endcall %}

일반 CSS 속성을 사용하여 클래스나 요소 선택기로 구성요소 스타일을 지정하세요. 예:

[sourcecode:html]
<body>
  <p>Hello, Kitty.</p>
  <amp-img
    class="grey-placeholder"
    src="https://placekitten.com/g/500/300"
    srcset="/img/cat.jpg 640w,
           /img/kitten.jpg 320w"
    width="500"
    height="300"
    layout="responsive">
  </amp-img>
</body>
[/sourcecode]

{% call callout('중요', type='caution') %}
 내 스타일이 AMP 에서 지원되는지 확인하세요. 일부 스타일은 성능상의 이유로 지원되지 않습니다([지원되는 CSS ](/ko/docs/guides/responsive/style_pages.html) 
참조).
{% endcall %}

## 반응형 요소 레이아웃

`width` 및 `height` 속성을 제공하여 표시되는 모든 AMP 요소의 크기와 위치를 지정합니다. 이 속성은 요소의 가로 세로 비율을 의미하며, 그 후 컨테이너에 맞춰 크기를 조정할 수 있습니다.

레이아웃을 반응형으로 설정합니다. 이렇게 하면 컨테이너 요소의 너비에 맞춰 요소의 크기를 조정하고, 너비 및 높이 속성으로 결정된 가로 세로 비율에 맞춰 자동으로 높이를 재조정합니다.

{% call callout('읽어보기', type='read') %}
  [AMP 에서 지원되는 요소](/ko/docs/guides/responsive/control_layout.html) 를 자세히 알아보세요.
{% endcall %}

## 자리표시자 및 대체 제공

자리표시자 및 대체가 내장되어 지원되므로 사용자에게 빈 화면이 표시되지 않습니다.

{% call callout('읽어보기', type='read') %}
 자리표시자 및 대체 [자세히 알아보기](/ko/docs/guides/responsive/placeholders.html)
{% endcall %}

## 이미지 아트 디렉션

AMP 는 `srcset` 과 `sizes` 속성을 모두 지원하여 어떤 이미지가 어떤 시나리오에서 로드될지 세밀하게 제어할 수 있습니다.

{% call callout('읽어보기', type='read') %}
  [크기 및 srcset으로 아트 디렉션하는 방법](/ko/docs/guides/responsive/art_direction.html) 자세히 알아보기
{% endcall %}

## 스타일 및 레이아웃 확인

AMP 검사기를 사용하여 페이지의 CSS 와 레이아웃 값을 테스트할 수 있습니다.

 검사기는 페이지의 CSS 가 50,000바이트 한도를 넘지 않는지, 허용되지 않는 스타일이 있는지, 페이지의 레이아웃이 지원되며 올바른 형식인지 확인합니다. [스타일 및 레이아웃 오류 ](/ko/docs/reference/validation_errors.html#style-and-layout-errors) 의 전체 목록도 확인하세요.

50,000 바이트 한도를 초과하는 CSS 페이지로 인한 콘솔 오류 예:

<amp-img src="/static/img/docs/too_much_css.png" width="1404" height="334" layout="responsive"></amp-img>

{% call callout('읽어보기', type='read') %}
 [AMP 페이지 확인 및 오류 수정 ](/ko/docs/guides/validate.html) 방법 자세히 알아보기
{% endcall %}

