# find-the-middle-words
# c program
# Given a string for s, let's find the corresponding letter in the middle! s에 문자열이 주어지면 거기서 가운데에 해당되는 글자를 찾자!
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
#include <string.h>

char* solution(const char* s) {
    char* answer = (char*)malloc(3);
    int len=strlen(s);
    s+=len/2; //문자열포인터 s의 주소를 가운데로 이동
    if(len%2==0){
        s--; //한칸 뒤로
        strncpy(answer,s,2); //두글자를 복사
        answer[2]='\0'; //문자열 뒤 널문자추가
    }
    else{
        strncpy(answer,s,1); //한글자 복사
        answer[1]='\0';
    }
    return answer;
}
int main(void){
    solution("qwer");
    return 0;
}
# python
def solution(s):
    center=int(len(s)/2)
    if len(s)%2!=0:
        return s[center]
    else:
        return s[center-1:center+1]
a=solution("qwer")
print(a)
#result--> "we"
