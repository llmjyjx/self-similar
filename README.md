	写出html
	自同构性

	line_0：
	* 随机生成j个点 ，j<11,j>=6，j为偶数
	* 随机  point_0_1,point_0_2 ... point_0_j, xy范围（0-100，0-11300），point_0_j_y >8000,j个点均匀分布
	* 每个点x大于前一个，point_0_1_y < point_0_1_y，point_0_1_y > point_0_2_y，(也就是一高一低)
	* 顺序连接j个点

	line_n(n>0)：
	# 遍历line_n-1 所有线段，每一条线段内部：
	* 随机生成j个点 ，j<11,j>=6，j为偶数
	* 固定 point_n_1（point_n-1_1_x,point_n-1_1_y），point_n_j（point_n-1_j_x,point_n-1_j_y）(即第一条起点为line_n-1起点，最后一条终点为line_n-1终点)
	* 随机  point_n_1,point_n_2 ... point_n_j, x范围（line_n-1_j_x，line_n-1_j+1_x）,y范围（line_n-1_j_y，line_n-1_j+1_y）
	* 每个点x大于前一个，point_n_1_y < point_n_1_y，point_n_1_y > point_n_2_y，(也就是一高一低)
	* 顺序连接j个点

	默认level = 1，最大5级别，用 + - 按钮调节级别
	每个级别不同颜色，白 黄 红 绿 蓝 橙
	并且配置是否显示按钮，默认都显示，按钮数量同步 level
	可以像tradingview 滚动鼠标放大细节，右侧3% 宽度 显示y坐标条，下部3% 高度显示x坐标，
	* 鼠标在y条范围内滚动上下缩放y，其余位置左右缩放x
	* 鼠标在y条范围内按住上下拖动也是缩放y
