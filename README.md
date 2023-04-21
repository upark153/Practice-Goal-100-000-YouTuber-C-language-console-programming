# Practice-Goal-100-000-YouTuber-C-language-console-programming
This is a programming exercise to achieve 100,000 YouTubers in c language.
![image](https://user-images.githubusercontent.com/115389450/233521624-781f3850-770e-4be9-825d-840cfb9e11ba.png)
```
#include <stdio.h> // main 함수 사용하기 위해서
#include <stdlib.h> // rand함수 srand 함수 사용하기 위해서
#include <time.h> // 시간 함수

// 유튜브 채널이름 입력
// 오늘의 컨텐츠 입력을 하면 방송송출~! 시작
// 시청자가 (1초마다) 50명~2500명 사이로 랜덤 증가
// (총 10초동안) 시청자 증가수를 변수에 저장
// 시청자 증가수 나누기 1~5를 랜덤으로 하여 구독자 수 증가
// 상기 방송송출 총20번
// 10만 유튜버가 되면 실버버튼 증정 성공
// 안되면 유튜브채널 폭파

int main(void)
{
    char youtube[50]; // 유튜브 채널 입력
    char contents[50]; // 콘텐츠 입력
    int viewers=0; // 시청자 수
    int total_viewers=0; // 1번 방송송출이 완료되었을 때 전체 시청자 수
    int subscriber=0; // 구독자 수
    int total_subscriber=0; // 1번 방송송출이 완료되었을 때 전체 구독자 수
    int random=0; // 시청자수 나누기 1~5를 하기 위한 변수!
    srand(time(0)); // 매번 다른 값을 주기위한 난수!

    printf("유튜브 채널 입력 : ");
    scanf("%s", youtube);
    printf("\n오늘의 컨텐츠 입력 : ");
    scanf("%s", contents);
    for(int j=1; j<=20;j++) // 20번 반복할겁니다!! 방송송출을!!
        {
            printf("방송송출 시작~!!\n");
            printf("++++++++++++방송송출 %d번째!++++++++++++", j); // 
            total_viewers=0;  // 값을 초기화해줬습니다! 왜냐하면 방송송출 1번이 끝나고 2번방송부터 0명부터 시작하기 때문!
            for(int i=1; i<=10; i++) // 1초 몇명, 2초 몇명, 3초몇명...10초 몇명을 주기위한 반복!
            {
                printf("\n%d초 지났습니다.\n", i);
                viewers=rand()%2500+50;
                printf("시청자 증가수는 %d명입니다.\n", viewers);
                total_viewers+=viewers;
                printf("총 시청자 수는 %d명입니다.\n", total_viewers);
            }
            random=rand()%5+1; 
            subscriber=total_viewers/random;
            printf("\n++오늘의 컨텐츠++\n<%s> 컨텐츠 %d번째 방송 구독자 수는 %d명입니다.\n",contents, j, subscriber);
            total_subscriber+=subscriber;
            printf("총 구독자 수는 %d명입니다.\n", total_subscriber);
            if(total_subscriber>=100000)
            {
                printf("10만유튜버가 되었습니다! 실버버튼 증정!\n");
                break;
            }
            else if(total_subscriber<100000)
            {
                printf("++10만유튜버가 되기까지 %d명 남았습니다++\n", 100000-total_subscriber);
            }
        }
        if(total_subscriber<100000)
            printf("\n!!!!<20>번의 방송동안 \n구독자수가 10만명이 되지 못하여 \n유튜브채널 폭파되었습니다.ㅜㅜ!!!!\n");    
    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233521690-ff672294-8fed-4d5e-b61f-a89c608013ea.png)
![image](https://user-images.githubusercontent.com/115389450/233521712-5b4dc35a-c90e-4db5-a294-b20b0d9b67ef.png)
- - - 
배 열 공 부
- - -
![image](https://user-images.githubusercontent.com/115389450/233521792-912319bd-8c65-4052-85b8-cf3edba61785.png)
```
#include <stdio.h>

int main(void)
{
    int ary[5];  // int형 요소 5개의 배열 선언

    ary[0] = 10; // 첫 번째 배열 요소에 10 대입
    ary[1] = 20; // 두 번째 배열 요소에20 대입
    ary[2] = ary[0] + ary[1]; // 첫 번째와 두 번째 요소를 더해 세 번째 저장
    scanf("%d", &ary[3]); // 키보드로 4번째 요소 입력

    printf("%d\n", ary[2]); // 세번째 배열 요소 출력
    printf("%d\n", ary[3]);
    printf("%d\n", ary[4]); // 마지막 배열요소는 쓰레기 값

    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233521899-c3d14b5f-670a-4cc4-bde7-cd4e132984bc.png)

```
#include <stdio.h>

int main(void)
{
    int num[10] = {1, 3, 6, -3, 4, -1, 0, -5, -5, 7};
    int i=0, count=0;

    for(i=0; i<10; i++)
    {
        if(num[i]>0)
        {
            count++;
        }
    }
    printf("양수는 %d개입니다.\n", count);
}
```
![image](https://user-images.githubusercontent.com/115389450/233521935-2ad52949-14f5-4284-8d6e-707b271937d3.png)
![image](https://user-images.githubusercontent.com/115389450/233521961-09dfc7bd-3065-402d-b9e1-162f46c0a265.png)
```
#include <stdio.h>

int main(void)
{
    int ages[28]; // 28명의 나이를 저장할 배열
    int total=0; // 총합을 저장할 변수, 미리 0으로 초기화한다.
    double age;  // 평균나이를 저장할 변수
    int i;      // 반복 제어 변수
    printf("28명의 나이를 입력하세요 : ");
    for(i=0; i<28; i++)
    {
        scanf("%d", &ages[i]); // 각 배열요소에 나이 입력
    }
    for(i=0; i<28; i++)
    {
        total+=ages[i]; // 모든 배열요소의 값을 누적시킨다.
    }
    age=total/28.0; // 평균 나이 계산.
    printf("입력된 28명의 나이: ");
    for(i=0; i<28; i++)
    {
        printf("%d", ages[i]); // 각 배열 요소의 값을 출력
    }
    printf("\n 28명의 평균 나이는 %.1lf입니다.\n", age); //평균 나이 출력
    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233521998-a1f3e5d7-7106-45f9-9c7a-1ade82a45166.png)
```
#include <stdio.h>

int main(void)
{
    int ary1[5] = {1,2,3,4,5}; 
    int ary2[5] = {1,2,3}; // 초기값이 적은 경우
    int ary3[] = {1,2,3}; // 배열 요소 개수가 생략된 경우
    double ary4[5] = {1.0, 2.1, 3.2, 4.3, 5.4}; //double 형 배열 초기화
    char ary5[5] = {'a', 'p', 'p', 'l', 'e'}; // char형 배열 초기화

    ary1[0] = 10;
    ary1[1] = 20;
    ary1[2] = 30;
    ary1[3] = 40;
    ary1[4] = 50;

    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233522072-29c3d29a-4c37-4cc2-8232-5bbcd07ead3c.png)
![image](https://user-images.githubusercontent.com/115389450/233522094-e1e3cabc-4576-4632-9177-5a7bdab32b06.png)
```
#include <stdio.h>

int main(void)
{
    int score[5];

    scanf("%d", &score[0]);
    scanf("%d", &score[1]);
    scanf("%d", &score[2]);
    scanf("%d", &score[3]);
    scanf("%d", &score[4]);

    return 0;
}
```
- - -
바뀌는 것은 첨자 분 > 반복문 사용 가능
배열과 반복문 사용한 성적처리 프로그램 예제
- - -
```
#include <stdio.h>

int main(void)
{
    int score[5];
    int i;
    int total=0;
    double avg;

    for(i=0; i<5; i++)
    {
        scanf("%d\n", &score[i]);
    }
    for(i=0; i<5; i++)
    {
        total+=score[i]; // 성적을 누적하여 총점 계산
    }
    avg= total/5.0; // 평균 계산
    for(i=0; i<5; i++)
    {
        printf("%5d", score[i]);
    }
    printf("\n");
    printf("평균 : %.1lf\n", avg); // 평균 출력
    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233522175-28d79b7a-19d6-42b9-9f8c-cfbb676967d8.png)
```
#include <stdio.h>

int main(void)
{
    int score[5];
    int i;
    int total=0;
    double avg;
    int count;      // 배열 요소 수를 저장할 변수

    count = sizeof(score) / sizeof(score[0]); // 배열 요소 수 계산

    for(i=0; i<count; i++) // 11행에서 계산한 count만큼 반복
    {
        scanf("%d", &score[i]);
    }
    for(i=0; i<count; i++)
    {
        total+=score[i];
    }
    avg=total/(double)count;

    for(i=0; i<count; i++)
    {
        printf("%5d", score[i]);
    }
    printf("\n");
    printf("평균 : %.1lf", avg);

    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233522232-fd0f0cf8-4e36-4d3c-9749-3f11030b4fb0.png)
![image](https://user-images.githubusercontent.com/115389450/233522275-0632eb31-d17d-4b8f-bd0d-725788b737ae.png)
```
#include <stdio.h>

int main(void)
{
    char str[80] = "apllejam"; // 문자열 초기화

    printf("최초 문자열: %s\n", str); // 초기화 문자열 출력
    printf("문자열 입력 : ");
    scanf("%s", str); // 새로운 문자열 입력
    printf("입력 후 문자열: %s\n", str); // 입력된 문자열 출력

    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233522311-622934a2-787f-4882-a5e1-3d97be474395.png)
- - -
﻿
문자를 저장하는 배열.

- 문자열을 대입하는 strcpy 함수 예제

﻿
- - -
```
#include <stdio.h>
#include <string.h> // 문자열 다루는 함수들의 원형 모아놓음. strcpy함수에 접근하기 위해 사용

int main(void)
{
    char str1[80] = "cat";
    char str2[80];

    strcpy(str1, "tiger"); // str1배열에 tiger 복사
    strcpy(str2, str1);    // str2배열에 str1배열의 문자열 복사
    printf("%s, %s\n", str1, str2);

    return 0;
}
```
- - -
﻿
문자열 전용 입출력 함수( gets, puts )

- gets 함수

> 빈 칸을 포함하여 한 줄 전체를 문자열로 입력

> 문자열 출력 함수 puts 와 같이 쓰임


두 함수의 함수 원형?

﻿
- - -
```
char *gets(char *str)
int puts(const char *str)
```
```
#include <stdio.h>

int main(void)
{
    char str[80];

    printf("문자열 입력 : "); // 입력 안내 메시지 출력
    gets(str);               // 빈칸을 포함한 문자열 입력
    puts("입력된 문자열: "); // 문자열 상수 출력
    puts(str);              // 배열에 저장된 문자열 출력

    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233522408-b989d018-b71a-4345-8a9b-6c9157d24070.png)








