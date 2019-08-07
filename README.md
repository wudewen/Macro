# Macro
常用的宏定义

// 通知
#define NC  [NSNotificationCenter defaultCenter]

// 偏好设置
#define NS [NSUserDefaults standardUserDefaults]

// 屏幕宽高
#define SCREEN_WIDTH [[UIScreen mainScreen] bounds].size.width
#define SCREEN_HEIGHT [[UIScreen mainScreen] bounds].size.height

// 屏幕比例适配系数
#define BR_IS_IPHONE (UI_USER_INTERFACE_IDIOM() == UIUserInterfaceIdiomPhone)
#define BR_IS_PAD (UI_USER_INTERFACE_IDIOM()== UIUserInterfaceIdiomPad)
#define kScaleFit (BR_IS_IPHONE ? ((SCREEN_WIDTH < SCREEN_HEIGHT) ? SCREEN_WIDTH / 375.0f : SCREEN_WIDTH / 667.0f) : 1.1f)

// 颜色
#define RGB(r,g,b) [UIColor colorWithRed:r/255.0 green:g/255.0 blue:b/255.0 alpha:1.0];
#define RGBA(r,g,b,a) [UIColor colorWithRed:r/255.0 green:g/255.0 blue:b/255.0 alpha:a];
#define ColorWithHexString(rgbValue) [UIColor colorWithRed:((float)((rgbValue & 0xFF0000) >> 16))/255.0 green:((float)((rgbValue & 0xFF00) >> 8))/255.0 blue:((float)(rgbValue & 0xFF))/255.0 alpha:1.0]

#define KClearColor [UIColor clearColor]
#define KWhiteColor [UIColor whiteColor]
#define KBlackColor [UIColor blackColor]
#define KRedColor [UIColor redColor]
#define KCyanColor [UIColor cyanColor]
#define KYellowColor [UIColor yellowColor]
#define KGrayColor [UIColor grayColor]
#define KGreenColor [UIColor greenColor]
#define KPurpleColor [UIColor purpleColor]
#define KLightGrayColor [UIColor lightGrayColor]


// 打印信息NSLog
#ifdef DEBUG    // 判断是不是开发、调试状态，如果是开发调试状态就让WDWLog替换WDWLog
#define WDWLog(...) NSLog(__VA_ARGS__) //WDWLog是不限制参数的，中间用三个英文句号表示
#elif   // 如果是发布状态就WDWLog就直接为空
#define WDWLog(...)
#endif
