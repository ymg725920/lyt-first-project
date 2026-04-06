# lyt-first-project
lyt的第一个GitHub测试项目
# 简易图书管理系统

## 项目介绍
这是一个基于Python开发的入门级简易图书管理系统，用于学习和实践GitHub仓库创建、README文档编写规范，同时掌握Python基础编程语法。

## 使用方法
本项目是一个轻量化的图书管理工具，核心用途是帮助用户快速管理个人图书信息，支持图书的添加、查询、展示等基础操作，适合编程初学者作为第一个GitHub项目进行学习和实践，同时也可用于小型场景下的图书信息管理。

1. 将项目中的`book_system.py`代码复制到本地Python文件中，使用Python 3.x环境直接运行
2. 根据控制台菜单提示，输入对应功能编号，即可完成图书的添加、查询、展示等操作

## 核心代码
```python
# 简易图书管理系统
# 用于存储所有图书信息的列表
book_list = []

# 添加图书功能
def add_book():
    book_name = input("请输入图书名称：")
    author = input("请输入作者名称：")
    book_info = {"书名": book_name, "作者": author}
    book_list.append(book_info)
    print("✅ 图书添加成功！")

# 查询图书功能
def search_book():
    search_name = input("请输入要查询的图书名称：")
    for book in book_list:
        if book["书名"] == search_name:
            print(f"🔍 找到图书：{book}")
            return
    print("❌ 未找到该图书")

# 展示所有图书功能
def show_all_books():
    if not book_list:
        print("📚 暂无图书信息")
        return
    print("\n===== 所有图书列表 =====")
    for index, book in enumerate(book_list, 1):
        print(f"{index}. 书名：{book['书名']} | 作者：{book['作者']}")

# 主菜单
def main_menu():
    while True:
        print("\n===== 简易图书管理系统 =====")
        print("1. 添加图书")
        print("2. 查询图书")
        print("3. 查看所有图书")
        print("0. 退出系统")
        choice = input("请输入您的选择：")
        
        if choice == "1":
            add_book()
        elif choice == "2":
            search_book()
        elif choice == "3":
            show_all_books()
        elif choice == "0":
            print("👋 退出系统成功")
            break
        else:
            print("⚠️ 输入无效，请重新输入")

if __name__ == "__main__":
    main_menu()
