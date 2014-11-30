---
layout: default
title: python 内置方法练习
---
````python
#coding:utf-8
class storage(dict):
    #通过使用__setattr__, __getattr__, __delattr__
    #可以重写dict，使之通过“.”调用
    def __setattr__(self, key, value):
        print "in __setattr__ methon"
        self[key] = value
    def __getattr__ (self, key):
        try:
            print "in __getattr__ methon"
            return self[key]
        except KeyError, k:
            return None
    def __delattr__ (self, key):
        try:
            print "in __delattr__ methon"
            del self[key]
        except KeyError, k:
            return None

# __call__方法用于实例自身的调用
#达到()调用的效果
    def __call__ (self, key):
        try:
            print "in __call__ methon"
            return self[key]
        except KeyError, k:
                return None

s = storage()
s.name = "hello"   #这是__setattr__起的作用
print s("name")    #这是__call__起的作用
print s["name"]    #dict默认行为
print s.name       #这是__getattr__起的作用
#del s.name         #这是__delattr__起的作用
print s("name")
print s["name"]
print s.name 
````
