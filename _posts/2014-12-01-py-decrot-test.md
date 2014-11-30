---
layout: default
title: python 类装饰器练习
---

````python
# coding: utf8
class A(object):
    def __init__(self, func,name=''):
        self.func = func
    def __call__(self):
        return self.func() + 20
dector = A        
@dector
def a():
    return 10
 
def b():
    return 30
 
print(a())  
 
c=A(a) #this means calling A(A(a)) , so 20+20+10

print c
print c()
 
d=A(b) # 30+20
print d()
 
print(a()) 



class Route(object):

    _routes = {}

    def __init__(self, pattern, kwargs={}, name=None, host='.*$'):
        self.pattern = pattern
        self.kwargs = {}
        self.name = name
        self.host = host
    # 对象通过提供__call__(slef, [,*args [,**kwargs]])方法可以模拟函数的行为，
    # 如果一个对象x提供了该方法，就可以像函数一样使用它，也就是说x(arg1, arg2...) 等同于调用x.__call__(self, arg1, arg2) 
    def __call__(self, handler_class):
        spec = (self.pattern, handler_class, self.kwargs, self.name)
        self._routes.setdefault(self.host, []).append(spec)
        return handler_class

    @classmethod
    def routes(cls, application=None):
        if application:
            for host, handlers in cls._routes.items():
                application.add_handlers(host, handlers)
        else:
            return reduce(lambda x,y:x+y, cls._routes.values()) if cls._routes else []
route=Route

@route('/hello',name='hello')
class HelloHandler():
    pass
@route('/hi',name='hi')
class HiHandler():
    pass


@route('/hi',name='hi')
def Hi01Handler():
    pass
#HelloHandler()
#HiHandler()
print Route._routes
print Route._routes.values()
print reduce(lambda x,y:x+y, Route._routes.values())
print Route.routes()
    
print reduce(lambda x,y:x+y,[['a','a1'],['b']])
print reduce(lambda x,y:x+y,[['a','a1',['as']],['b','b2','b3']])
print ['a','a1']+['b','b2','b3']
# __call__ test
class DistanceForm(object):
    def __init__(self, origin):
        self.origin = origin
        print "origin :"+str(origin)
    def __call__(self, x):
        print "x :"+str(x)
 
p = DistanceForm(100)
p(2000)
 
输出
>>> 
origin :100
x :2000
````
