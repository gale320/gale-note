STM32F4的随机数发生器RNG，以环境噪声为种子，产生32位随机数供主机使用。

【主要特性】

1、产生32位随机数  2、两次转换时间间隔40PLL48CLK   3、随机数熵检测以发现不正常位，以产生稳定序列  3、可被关闭以省电

【实验过程】

产生一个随机数，编译器跟踪查看随机数

【代码实现】

RNG只有三个寄存器CR、SR和DR。配置信息写在CR，状态信息可从SR读取，产生的随机数存放在DR中。

首先，使能RNG时钟

RCC_AHB2PeriphClockCmd(RCC_AHB2Periph_RNG,ENABLE);

然后，启动RNG

RNG_Cmd(ENABLE);

最后等待随机数产生完毕标志，读数即可

while(RNG_GetFlagStatus(RNG_FLAG_DRDY) == RESET);  //等待随机数准备完毕
data = RNG_GetRandomNumber();   //读数
