以下是按实际开发与学习频率整理的 **MATLAB 核心高频基础函数速查表**，涵盖日常使用率最高的 6 大功能模块。

---

### 1. 工作区与文件管理（Workspace & File I/O）

| 函数名 | 用途说明 | 简单示例 |
| --- | --- | --- |
| `clc` | 清空命令行窗口（Command Window）显示内容 | `clc` |
| `clear` | 清除工作区（Workspace）中的变量 | `clear` 或 `clear x y` |
| `close all` | 关闭所有打开的图形窗口（Figure） | `close all` |
| `whos` | 查看当前工作区所有变量的名称、维度、字节数及类型 | `whos` |
| `save` / `load` | 将工作区变量保存为 `.mat` 文件 / 从 `.mat` 文件加载 | `save('data.mat', 'A')` |
| `readtable` | 读取 Excel 或 CSV 表格数据为 `table` 类型（推荐） | `T = readtable('data.csv');` |
| `writetable` | 将 `table` 数据写入 Excel 或 CSV 文件 | `writetable(T, 'out.xlsx');` |
| `disp` / `fprintf` | 在命令行打印变量内容 / 格式化输出文本与数值 | `fprintf('结果: %.2f\n', val);` |

---

### 2. 矩阵创建与维度操作（Matrix Creation & Manipulation）

| 函数名 | 用途说明 | 简单示例 |
| --- | --- | --- |
| `zeros` / `ones` | 创建全 0 矩阵 / 全 1 矩阵 | `A = zeros(3, 4);` |
| `eye` | 创建单位矩阵（主对角线为 1） | `I = eye(3);` |
| `rand` / `randn` | 生成 `[0, 1]` 均匀分布 / 标准正态分布随机数矩阵 | `R = randn(2, 5);` |
| `linspace` | 在指定区间内生成等间距向量 | `x = linspace(0, 10, 100);` |
| `size` / `length` | 获取矩阵各维度大小 / 获取向量的最大维度长度 | `[r, c] = size(A);` |
| `numel` | 返回矩阵中的元素总个数 | `n = numel(A);` |
| `reshape` | 在元素总数不变的前提下重塑矩阵维度 | `B = reshape(A, 2, 6);` |
| `find` | 查找满足条件的非零元素索引（线性索引或行列下标） | `idx = find(x > 5);` |
| `sort` | 对向量或矩阵按升序或降序排列 | `[B, idx] = sort(x, 'descend');` |

---

### 3. 基础数学与统计计算（Math & Statistics）

| 函数名 | 用途说明 | 简单示例 |
| --- | --- | --- |
| `sum` / `prod` | 计算数组元素之和 / 乘积（默认按列计算） | `s = sum(A, 2);`（按行求和） |
| `mean` / `median` | 计算平均值 / 中位数 | `m = mean(x);` |
| `std` / `var` | 计算标准差 / 方差 | `sd = std(x);` |
| `max` / `min` | 求最大值 / 最小值（可同时返回索引位置） | `[val, pos] = max(x);` |
| `abs` | 计算实数绝对值或复数模长 | `y = abs(-3 + 4i);`（返回 `5`） |
| `round` / `floor` / `ceil` | 四舍五入 / 向下取整 / 向上取整 | `r = round(3.1415, 2);`（返回 `3.14`） |
| `mod` / `rem` | 取模（余数符号与除数相同）/ 求余（余数符号与被除数相同） | `r = mod(10, 3);`（返回 `1`） |
| `exp` / `log` / `log10` | 自然指数 $e^x$ / 自然对数 $\ln(x)$ / 常用对数 $\lg(x)$ | `y = log(exp(2));`（返回 `2`） |
| `sin` / `cos` / `atan2` | 正弦 / 余弦（弧度制）/ 四象限反正切 | `theta = atan2(y, x);` |

---

### 4. 线性代数与多项式（Linear Algebra & Polynomials）

| 函数名 | 用途说明 | 简单示例 |
| --- | --- | --- |
| `inv` / `pinv` | 求方阵的逆矩阵 / 求任意矩阵的伪逆 | `A_inv = inv(A);` |
| `\`（反斜杠） | 求解线性方程组 $Ax = b$（比 `inv(A)*b` 更快、精度更高） | `x = A \ b;` |
| `det` / `rank` / `trace` | 计算方阵行列式 / 矩阵的秩 / 矩阵的迹 | `r = rank(A);` |
| `eig` | 计算方阵的特征值和特征向量 | `[V, D] = eig(A);` |
| `svd` | 奇异值分解（Singular Value Decomposition） | `[U, S, V] = svd(A);` |
| `polyfit` / `polyval` | 多项式曲线拟合 / 计算多项式在指定点的值 | `p = polyfit(x, y, 2);` |
| `roots` | 求多项式方程的所有根 | `r = roots([1, -3, 2]);`（解 $x^2-3x+2=0$） |

---

### 5. 数据可视化与基础绘图（Plotting & Graphics）

| 函数名 | 用途说明 | 简单示例 |
| --- | --- | --- |
| `figure` | 创建一个新的独立图形窗口 | `figure('Name', '测试图');` |
| `plot` | 绘制二维线性折线图/曲线图 | `plot(x, y, 'r--', 'LineWidth', 1.5);` |
| `scatter` | 绘制二维散点图 | `scatter(x, y, 30, 'filled');` |
| `bar` / `histogram` | 绘制柱状图 / 统计直方图 | `histogram(randn(1000, 1), 20);` |
| `surf` / `imagesc` | 绘制三维曲面图 / 将矩阵显示为伪彩色图像（热力图） | `imagesc(A); colorbar;` |
| `subplot` / `tiledlayout` | 在同一窗口创建多个子图网格（新版推荐 `tiledlayout`） | `subplot(2, 1, 1);` |
| `hold on` / `hold off` | 保持当前坐标系，使后续绘图叠加在同一张图上 | `hold on; plot(x, y2);` |
| `title` / `xlabel` / `ylabel` | 添加图标题、X 轴标签、Y 轴标签 | `title('正弦波形'); xlabel('时间 (s)');` |
| `legend` / `grid on` | 添加图例说明 / 显示背景网格线 | `legend('信号1', '信号2'); grid on;` |
| `xlim` / `ylim` | 手动设置 X 轴或 Y 轴的显示范围 | `xlim([0, 10]);` |

---

### 6. 逻辑判断与流程控制（Logic & Control Flow）

| 函数名 / 关键字 | 用途说明 | 简单示例 |
| --- | --- | --- |
| `any` / `all` | 判断向量或矩阵中是否“存在任意非零元素” / “全部非零” | `if any(x < 0), disp('含负数'); end` |
| `isnan` / `isinf` / `isempty` | 检测元素是否为 `NaN`（缺失值）/ 无穷大 / 数组是否为空 | `x(isnan(x)) = 0;`（缺失值补零） |
| `strcmp` / `contains` | 比较两个字符串是否完全相同 / 判断是否包含子字符串 | `tf = contains(str, 'MATLAB');` |
| `if ... elseif ... else` | 条件分支语句 | `if a > 0, b = 1; else, b = 0; end` |
| `for` / `while` | 固定次数循环 / 条件循环 | `for i = 1:10, s = s + i; end` |
| `tic` / `toc` | 成对使用，精确测量代码段的运行耗时（秒） | `tic; A = inv(rand(1000)); toc` |

