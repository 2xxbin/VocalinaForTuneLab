# VocalinaForTuneLab

> 본 프로그램은 **티젠스의 명시적 허락하에 개발되었으며**, **소스코드 비공개 조건**으로 배포 협의가 완료되었습니다. <br>
> 모든 저작권은 티젠스에 있으며, 본 프로그램을 허용된 사용 범위를 벗어난 **역설계, 소스 분석, 데이터 추출** 등의 행위는 금지됩니다. <br>
> 또한 원작자의 허락 없이 무단 복제, 배포, 수정할 수 없으며, 프로그램은 사전 고지 없이 언제든 배포 중단 될 수 있습니다.

티젠스의 음성합성엔진 `보카리나`를 오픈소스 에디터 [`TuneLab`](https://github.com/LiuYunPlayer/TuneLab)으로 이식한 프로그램입니다.

64 비트 Windows 전용이며, 32비트 및 기타 OS에서는 정상 작동을 보장하지 않습니다.

## 데모

### Voclina 2.2

https://github.com/user-attachments/assets/1607c9db-8f1c-41ef-aa80-7eef4db90b0f

- 가수: VORA (Vocalina 2.2)
- 원곡: [Dream (VORA 데모곡)](https://www.youtube.com/watch?v=N-_DIthRrQc)
- INST는 보카리나 스튜디오의 샘플 VSP 중, `Dream(v.카일린).vsp`의 내부 INST를 사용하였습니다.

### Voclina 2.3

VIDEO TBD

- 가수: Khylin (Vocalina 2.3)
- 원곡: [Dream (VORA 데모곡)](https://www.youtube.com/watch?v=N-_DIthRrQc)
- INST는 보카리나 스튜디오의 샘플 VSP 중, `Dream(v.카일린).vsp`의 내부 INST를 사용하였습니다.

## 지원 파라미터

- `Audio Start Offset (sec)`: 트랙의 출력 오디오 타이밍을 전체적으로 조절합니다. 전체적으로 박자가 밀리거나 빠를 경우 해당 파라미터를 조절해 싱크를 맞춰주세요.
- `Velocity`: 보카리나의 벨로시티입니다. 0부터 127의 범위를 가지며, 자음의 타이밍을 조정합니다.
- `Gain`: 트랙의 게인을 조정합니다. 볼륨이 너무 크거나 작을 때 조정해주세요.
- `Volume`: 볼륨 오토메이션입니다. 다이나믹 조교에 사용됩니다.

추가적로, 피아노 롤의 아래 노트 경계를 조정해 노트 길이를 수정하여 박자를 맞출 수 있습니다.
기존 보카리나의 파라미터(`Gender`, `Hamonic`, `EQ`, `Echo`, `Reverb`, `Pitch`)는 지원되지 않습니다.

## 알려진 문제점

1. `TuneLab`이 정상적으로 종료되지 않을 경우, 재실행되지 않습니다.
> 작업관리자에서 `TuneLab`, `Vocalina22RenderServer (32비트)`, `Vocalina23RenderServer (32비트)`를 강제종료 후 재실행해 주세요.

2. `Vocalina 2.2` 에서 피치 조교 및 비브라토를 사용할 수 없습니다.
> 2.2 버전에서는 인토네이션 같은 피치 렌더링 기능이 없어 제외되었습니다.

4. 일본어 및 중국어 문자와 한국어 로마자를 사용할 수 없습니다.
> 추후 포네마이저 방식으로 추가 예정입니다.

4. `TuneLab` 실행 속도가 조금 느려질 수 있습니다.

## 설치 방법

설치에 앞서, 사용하려는 보카리나 버전의 스튜디오와 유저 패치가 설치되어 있어야 합니다. <br>
[설치 파일 및 유저 패치는 아래에서 다운로드 가능합니다.](https://cafe.naver.com/f-e/cafes/27638112/articles/2326?boardtype=L&menuid=1&referrerAllArticles=false)

1. [`TuneLab` 릴리즈 페이지](https://github.com/LiuYunPlayer/TuneLab/releases/)에서 최선 버전을 다운로드합니다.
2. 압축 해제 후, 폴더 내부 `TuneLab.exe`를 실행합니다.
3. [`VocalinaForTuneLab` 릴리즈 페이지](https://github.com/LiuYunPlayer/TuneLab/releases/)에서 **본인이 사용할 보카리나 버전의 확장을** 다운로드합니다.
4. 실행된 `TuneLab`에 `.tlx` 파일을 드래그해 보카리나 확장을 설치합니다.
5. `TuneLab`을 종료 후 재실행하여 보이스 목록에 `Vocalina 2.X`가 뜨는지 확인합니다.
6. 정상적으로 동작하는지 테스트합니다.

만약 본인이 보카리나 설치 폴더가 기본 경로가 아닐 시, 설정 파일 편집이 필요합니다.

1. `Win + R`를 누른 뒤 `%Appdata%/TuneLab/Extensions`을 입력하여 폴더를 엽니다.
2. `Vocalina2X` 폴더 내부로 들어갑니다.
3. `config.json`을 메모장 등의 프로그램으로 열어 `"VocalinaInstallPath": "",`의 `""`을 지우고 본인의 설치 경로로 수정합니다. <br>
   (입력 시, `\`를 `\\`로 치환하여 적어주세요. ex: `C:\Program Files (x86)\` -> `C:\\Program Files (x86)\\`)
4. 파일을 저장 후, `TuneLab`을 실행해 작동을 확인해주세요.

## 로그 확인법

프로그램을 사용하다 보면 다양한 문제를 겪을 수 있습니다. 이 경우, 렌더링 서버를 표시하여 렌더링 로그를 확인할 수 있습니다.
렌더링 로그는 오류 발생 시 원인 파악에도 사용됩니다.

1. `Win + R`을 누른 뒤 `%Appdata%/TuneLab/Extensions`을 입력하여 폴더를 엽니다.
2. `Vocalina2X` 폴더 내부로 들어갑니다.
3. `config.json`을 메모장 등의 프로그램으로 엽니다.
4. `"IsEnableServerConsoleWindow": false`의 `false`를 `true`로 변경합니다.
5. 파일을 저장 후, `TuneLab`을 실행해 검은 터미널 창이 뜨는지 확인해주세요.
6. 문제를 재현한 뒤, 검은 터미널 창에 뜬 내용을 확인해주세요.
