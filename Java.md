# Java



## HashMap

Key不能重复

#### 1. 创建

```java
HashMap<String, Integer> map = new HashMap<>();
```

#### 2. 添加元素

```java
map.put("apple", 3);
map.put("banana", 2);
```

#### 3. 取数据

```Java
int count = map.get("apple");  // 3
```

#### 4. 判断是否存在

```Java
map.containsKey("apple");   // true
map.containsValue(3);       // true
```

#### 5. 删除元素

```Java
map.remove("apple");
```

#### 5. 获取大小

```Java
set.size();
```

#### 6. 遍历

##### 遍历Key

```Java
for (String key : map.keySet()) {
    System.out.println(key);
}
```

##### 遍历Key + value

```Java
for (Map.Entry<String, Integer> entry : map.entrySet()) {
    System.out.println(entry.getKey() + " " + entry.getValue());
}
```

### 常见用法：

#### 场景1：计数

```Java
HashMap<Integer, Integer> map = new HashMap<>();

for (int num : nums) {
    map.put(num, map.getOrDefault(num, 0) + 1);
}
```

#### 场景2：快速查找

```Java
map.get("apple");	// 3
```



## HashSet

1. 不允许重复
2. 查找快 O(1)
3. 无顺序

#### 1. 创建

```java
HashSet<Integer> set = new HashSet<>();
```

#### 2. 添加元素

```java
set.add(1);
```

#### 3. 判断是否存在

```Java
set.contains(1); // true
set.contains(3); // false
```

#### 4. 删除元素

```Java
set.remove(1);
```

#### 5. 获取大小

```Java
set.size();
```

#### 6. 遍历

```Java
for (int x : set) {
	System.out.println(x);
}
```

### 常见用法：

#### 场景1：去重

```Java
int[] nums = {1, 2, 2, 3};

HashSet<Integer> set = new HashSet<>();
for (int num : nums) {
    set.add(num);
}
```

#### 场景2：快速查找

```Java
HashSet<Integer> set = new HashSet<>();

for (int num : nums) {
    if (set.contains(target - num)) {
        return true;
    }
    set.add(num);
}
```

#### 场景3：判断重复

```java
HashSet<Integer> set = new HashSet<>();

for (int num : nums) {
    if (set.contains(num)) {
        return true;  // 有重复
    }
    set.add(num);
}
```



## Scanner

从输入中读取数据

#### 1. 创建

```java
Scanner sc = new Scanner(System.in);
```

#### 2. Function

- `nextInt()`：不会读掉换行字符
- `hasNextInt()`
- `nextLong()`
- `nextDouble()`
- `next()`：读到空格
- `nextLine()`

### 常见用法：

#### 场景1：数组输入

```Java
int n = sc.nextInt();
int[] nums = new int[n];

for (int i = 0; i < n; i++) {
    nums[i] = sc.nextInt();
}
```

#### 场景2：多组输入

```Java
while (sc.hasNext()) {
    int a = sc.nextInt();
    int b = sc.nextInt();
    System.out.println(a + b);
}
```

#### 场景3：存在换行

```java
int a = sc.nextInt();
sc.nextLine();  // 吃掉换行
String s = sc.nextLine();
```

#### 场景4：一行存在空格

```java
String line = sc.nextLine();
String[] parts = line.split(" ");
```



## BufferReader

专门按行读，比Scanner快

#### 1. 创建

```java
BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
```

#### 2. 读取一整行

```java
String line = reader.readLine();
```

#### 3. 读取一个整数

```java
int n = Integer.parseInt(reader.readLine());
```

#### 4. 读取一行多个数字

```java
String[] parts = reader.readLine().split(" ");

int a = Integer.parseInt(parts[0]);
int b = Integer.parseInt(parts[1]);
```

#### 5. 读取数组

```java
int n = Integer.parseInt(reader.readLine());
String[] parts = reader.readLine().split(" ");

int[] nums = new int[n];
for (int i = 0; i < n; i++) {
    nums[i] = Integer.parseInt(parts[i]);
}
```

#### 6. 多组输入

```java
String line;
while ((line = reader.readLine()) != null) {
    String[] parts = line.split(" ");
    int a = Integer.parseInt(parts[0]);
    int b = Integer.parseInt(parts[1]);
    System.out.println(a + b);
}
```



## StringBuilder

用来高效拼接字符串

- Stirng：每次修改=新建一个字符串
- StringBuilder：在原来的基础上进行改变

#### 1. 创建

```Java
StringBuilder sb = new StringBuilder();
```

#### 2. 拼接

```Java
sb.append("hello");
sb.append(" ");
sb.append("world");
```

#### 3. 转换为字符串

```Java
String s = sb.toString();
```

#### 4. 删除

```Java
sb.delete(0, 2);
```

#### 5. 插入

```Java
sb.insert(1, "abc");
```

#### 6. 反转

```Java
sb.reverse();
```

