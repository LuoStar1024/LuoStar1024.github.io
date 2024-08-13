---
title: C#代码规范
date: 2024-08-13 22:40:59
tags:
    - C# 
    - 代码规范
categories:
    - 编程语言
    - C#
---

## 对齐规范

1. 对齐方式为空格，缩进大小为4。

2. 大括号换行。

3. if 和 for 这种，不省略{}。

## 命名规范

1. 英文单词命名。禁止使用拼音或无意义的字母命名。

2. 直观易懂。使用能够描述其功能或有意义的英文单词或词组。

3. 不要采用下划线命名法。

```
int grand_value; // 错误：下划线命名。
```

4. 常量、静态变量、类、结构体、属性、方法等名称采用大驼峰命名法。

```
public const int MaxHp = 100; // 常量
public static float MaxSpeed = 100f; // 静态字段
public class GameLogic
{
    // 类
}
public struct Position
{
    // 结构体
}
public int Id
{
    // 属性
    get;
    set;
}
public void SendMessage(string message)
{
    // 方法
}
```

5. 公有字段、保护字段、私有字段、方法形参、局部变量采用小驼峰命名法。（私有字段以下划线开头

```
public int id; // 公有字段
protected string name; // 保护字段
private string _name; // 私有字段
public void SendMessage(string message) // 方法形参
{
    bool result = false; // 局部变量
}
```

6. 接口命名以大写字母 I 开头

```
public interface IState; // 接口
```

7. 枚举命名以大写字母 E 开头

```
public enum EGameType
{
    Simple,
    Hard
}
```



## 编码规范

1. 声明变量时，一行只声明一个变量。

2. 变量中，按共有、保护、私有分块

3. 类的字段声明统一放置于类的最前端。

4. 类的属性统一放置于类的字段和方法中间。

5. 一行代码长度不要超过屏幕宽度。如果超过了，将超过部分换行。

```
public class Student
{
    public int id;
    public int name;
    protected bool gender;
    private string _score; // 分数

    public int Age
    {
        get;
        set;
    }

    // 根据分数获取等级
    private int Level(int score)
    {
    
    }
}
```



## 注释规范

1. 公有和保护注释、类、枚举、结构体，采用///形式自动产生XML标签格式的注释。（私有可以不用注释

```
/// <summary>
/// 用户名
/// </summary>
public string userName;

/// <summary>
/// 用户名
/// </summary>
protected string userName;

/// <summary>
/// 用户名
/// </summary>
private string _userName;

private string _userName; // 用户名
```

2. 公有方法和保护方法注释，采用///形式自动产生XML标签格式的注释。（私有方法可以不用注释

```
/// <summary>
/// 通过用户ID获取用户名
/// </summary>
/// <param name="userId">用户ID</param>
/// <returns>返回用户名</returns>
public string GetUserNameById(int userId)
{
    // 代码
}

/// <summary>
/// 通过用户ID获取用户名
/// </summary>
/// <param name="userId">用户ID</param>
/// <returns>返回用户名</returns>
protected string GetUserNameById(int userId)
{
    // 代码
}

// 通过用户ID获取用户名
private string GetUserNameById(int userId)
{
    // 代码
}
```

3. 方法内的代码块注释。

```
public void UpdateLogic()
{
    // 攻击逻辑

    // 移动逻辑

    // 其他逻辑
}
```
