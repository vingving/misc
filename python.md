*args

- 파라미터를 몇개를 받을지 모르는 경우 사용한다. args 는 튜플 형태로 전달된다.

예)

def print_param(*args):
    print args
    for p in args:
        print p

print_param('a', 'b', 'c', 'd')
#('a', 'b', 'c', 'd')
#a
#b
#c
#d

**kwargs

- 파라미터 명을 같이 보낼 수 있다. kwargs는 딕셔너리 형태로 전달된다.

def print_param2(**kwargs):
    print kwargs
    print kwargs.keys()
    print kwargs.values()

    for name, value in kwargs.items():
        print "%s : %s" % (name, value)

print_param2(first = 'a', second = 'b', third = 'c', fourth = 'd')

#{'second': 'b', 'fourth': 'd', 'third': 'c', 'first': 'a'}
#['second', 'fourth', 'third', 'first']
#['b', 'd', 'c', 'a']
#second : b
#fourth : d
#third : c
#first : a

그러면 두개를 같이 쓰는 경우는??

def print_param3(*args, **kwargs):
    print args
    print kwargs

print_param3('a', 'b')
#('a', 'b')
#{}

print_param3(third = 'c', fourth = 'd')
#()
#{'fourth': 'd', 'third': 'c'}

print_param3('a', 'b', third = 'c', fourth = 'd')
#('a', 'b')
#{'fourth': 'd', 'third': 'c'}


응용 해 보자

def print_param4(a, b, c):
    print a, b, c

p = ['a', 'b', 'c']
print_param4(*p)
#a b c

p2 = {'c' : '1', 'a' : '2', 'b' : '3'}
print_param4(**p2)
#2 3 1


출처: https://jhproject.tistory.com/109 [JH PROJECT]
