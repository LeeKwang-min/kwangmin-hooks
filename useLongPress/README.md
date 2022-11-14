# useLongPress

- 짧게 클릭/터치와 길게 클릭/터치 하는 경우를 구분지어 동작할 수 있도록 하는 커스텀 훅스

## 사용법

- Params
  - onLongPress: (event: any) => void : 길게 클릭/터치 하였을 때 동작할 핸들러 함수
  - onClick: (event: any) => void : 짧게 클릭/터치 하였을 때 동작할 핸들러 함수
  - { shouldPreventDefault = true, delay = 300 } = {} : 추가 옵션을 위한 객체
    - shouldPreventDefault: 터치에 대한 기본동작을 막을 것인가를 정한다.
    - delay: 얼마나 오랫동안 클릭/터치해야 onLongPress를 동작하도록 할 것인지를 정한다.

## 사용 예시 코드

```
import useLongPress from 'my-package-source';

export function Record({ checkupList }: IRecord) {
    ...

  const onLongPress = (e: any) => {
    // Write some logic when use long press(click/touch)
  };

  const onClick = (e: any) => {
    // Write some logic when use short press(click/touch)
  };

  const defaultOptions = {
    shouldPreventDefault: false,
    delay: 500,
  };

  const longPressEvent = useLongPress(onLongPress, onClick, defaultOptions);

  return(
    ...
    <div {...longPressEvent}>Click!</div>
    ...
  )
}
```

### 참고

- [useLongPress.ts](https://stackoverflow.com/questions/48048957/react-long-press-event)
