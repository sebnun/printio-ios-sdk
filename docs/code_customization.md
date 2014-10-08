Developer SDK Customization Reference
=====================================

### Sections:

   - [Initialization](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#initialization)
      - [-initWithEnvironment](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--initwithenvironment)
      - [-initWithViewController](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--initwithviewcontroller)
   - [Opening and closing](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#opening-and-closing)
      - [-open](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--open)
      - [-openWithOption](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--openwithoption)
      - [-presentFromViewController](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--presentfromviewcontroller)
      - [-viewController](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--viewcontroller)
      - [-close](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--close)
   - [Navigation bar](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#navigation-bar)
      - [-navigationBarColor:titleColor:leftButtonBackgroundColor:rightButtonBackgroundColor:titleButtonIcon](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--navigationBarColortitleColorleftButtonBackgroundColorrightButtonBackgroundColortitleButtonIcon)
      - [-setNavigationBarBackground](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--setNavigationBarBackground)
      - [-setNavigationBarBackgroundForCustomizeProduct](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--setNavigationBarBackgroundForCustomizeProduct)
      - [-setIconForBackButton](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--setIconForBackButton)
      - [-setStatusBarDark:hidden](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--setStatusBarDarkhidden)
      - [-setThreeButtonsNavigationBarSytle](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--setThreeButtonsNavigationBarSytle)
      - [-setNavigationBarSaveToCartBackgroundColor:titleColor:buttonBackgroundColor:buttonTitleColor](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--setNavigationBarSaveToCartBackgroundColortitleColorbuttonBackgroundColorbuttonTitleColor)
   - [Side menu](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#side-menu)
      - [-useSideMenuWithMenuIcon:background](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--usesidemenuwithmenuiconbackground)
      - [-sideMenuAddButtons](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--sideMenuAddButtons)
      - [-sideMenuHideOptionsHeader](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--sideMenuHideOptionsHeader)
      - [-sideMenuHideAccountsHeader](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--sideMenuHideAccountsHeader)
      - [-sideMenuHideInfoHeader](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--sideMenuHideInfoHeader)
      - [-sideMenuShowOptionsAsList](https://github.com/printdotio/printio-ios-sdk/blob/master/docs/code_customization.md#--sideMenuShowOptionsAsList)
   - Screens
   - 
   
### Initialization

######- initWithEnvironment
``` Objective-C
/**
 Init PrintIO widget. To get view controller, use '[self.printIO viewController]'

 @param type Set environment to staging or live, use PRINTIO_STAGING or PRINTIO_PRODUCTION
 @param pRecipeId Production recipeId provided by PrintIO
 @param sRecipeId Staging recipeId provided by PrintIO
 */
- (id)initWithEnvironment:(int)type
       productionRecipeId:(NSString *)pRecipeId
          stagingRecipeId:(NSString *)sRecipeId;
```
######- initWithViewController
``` Objective-C
/**
 Init PrintIO widget with parent view controller.

 @param viewController Parent view controller. From this view controller, widget will open.
 @param type Set environment to staging or live, use PRINTIO_STAGING or PRINTIO_PRODUCTION
 @param pRecipeId Production recipeId provided by PrintIO
 @param sRecipeId Staging recipeId provided by PrintIO
 */
- (id)initWithViewController:(id)viewController
                 environment:(int)type
          productionRecipeId:(NSString *)pRecipeId
             stagingRecipeId:(NSString *)sRecipeId;
```
### Opening and closing

######- open
``` Objective-C
/**
 Open widget by presenting view from bottom
 */
- (void)open;
```
######- openWithOption
``` Objective-C
/**
 Open widget with option

 @param option Set the options
 PRINTIO_OPTION_PRESENT_VIEW_FROM_LEFT,
 PRINTIO_OPTION_PRESENT_VIEW_FROM_RIGHT,
 PRINTIO_OPTION_PRESENT_VIEW_FROM_BOTTOM,
 PRINTIO_JUMP_TO_SCREEN_SHOPPING_CART
 PRINTIO_ENABLE_BACK_BUTTON
 */
- (void)openWithOption:(int)option;
```
######- presentFromViewController
``` Objective-C
/**
 Present widget from view controller with option
 
 @param option Set the options
 PRINTIO_OPTION_PRESENT_VIEW_FROM_LEFT,
 PRINTIO_OPTION_PRESENT_VIEW_FROM_RIGHT,
 PRINTIO_OPTION_PRESENT_VIEW_FROM_BOTTOM,
 PRINTIO_JUMP_TO_SCREEN_SHOPPING_CART
 PRINTIO_ENABLE_BACK_BUTTON
 */
- (void)presentFromViewController:(UIViewController *)viewController
                       withOption:(int)option;
```
######- viewController
``` Objective-C
/**
 Returns PrintIO view controller. Set all options before calling this method
 */
- (id)viewController;
```
######- close
``` Objective-C
/**
 Close widget
 */
- (void)close:(NSInteger)flag;
```
### Navigation bar

######- navigationBarColor:titleColor:leftButtonBackgroundColor:rightButtonBackgroundColor:titleButtonIcon
```Objective-C
/**
 Change navigation bar color and title font color.

 @param color Color for title bar (navigation bar). If nil default color is used.
 @param tColor Color of fonts on title bar. If nil default color is used.
 @param lColor Background color for left navigation bar button. If nil, transparent will be used.
 @param rColor Background color for right navigation bar button. If nil, transparent will be used.
 @param iPath Path to icon for button in the center of navigation bar. If nil, title will be shown, otherwise
 button will be shown. Click on button opens sub menu, which can be customized by PrintIO.
 */
- (void)navigationBarColor:(UIColor *)color
                titleColor:(UIColor *)tColor
 leftButtonBackgroundColor:(UIColor *)lColor
rightButtonBackgroundColor:(UIColor *)rColor
           titleButtonIcon:(NSString *)iPath;
```
######- setNavigationBarBackground
```Objective-C
/**
 Set background image on Navigation Bar
 
 @param imagePath Path to image file.
 */
- (void)setNavigationBarBackground:(NSString *)imagePath;
```
######- setNavigationBarBackgroundForCustomizeProduct
```Objective-C
/**
 Set navigation bar background image on 'Customize Product' screen
 
 @param imagePath Path to image file.
 */
- (void)setNavigationBarBackgroundForCustomizeProduct:(NSString *)imagePath;
```
######- setIconForBackButton
```Objective-C
/**
 Set icon for back button.

 @param path Path to image file.
 */
- (void)setIconForBackButton:(NSString *)iconPath;
```
######- setStatusBarDark:hidden
```Objective-C
/**
 Set status bar style and visibility.

 @param dark Default value is NO
 @param hidden Default value is NO
 */
- (void)setStatusBarDark:(BOOL)dark
                  hidden:(BOOL)hidden;
```
######- setThreeButtonsNavigationBarSytle
```Objective-C
/**
 Set three buttons Back, Menu and Cart button in navigation bar for Featured Products screen

 @param set Default value is NO
 */
- (void)setThreeButtonsNavigationBarSytle:(BOOL)set;
```
######- setNavigationBarSaveToCartBackgroundColor:titleColor:buttonBackgroundColor:buttonTitleColor
```Objective-C
/**
 Set colors scheme for navigation bar with "Save to" shopping cart button
 https://github.com/printdotio/printio-ios-sdk/blob/master/ios_sdk_customization.md#save-to-shopping-cart-button
 
 @param bcgColor Navigation bar background color
 @param titleColor Navigation bar title color
 @param btnBcgColor Button's background color
 @param btnTitleColor Button's title color
 */
- (void)setNavigationBarSaveToCartBackgroundColor:(UIColor *)bcgColor
                                       titleColor:(UIColor *)titleColor
                            buttonBackgroundColor:(UIColor *)btnBcgColor
                                 buttonTitleColor:(UIColor *)btnTitleColor;
```
###Side menu
######- useSideMenuWithMenuIcon:background
```Objective-C
/**
 Use Side Menu with options:

 @param mIconPath Path to image for Menu icon. If nil, default icon will be used.
 @param bcgColor Background color for Side Menu. If nil, default will be used.
 */
- (void)useSideMenuWithMenuIcon:(NSString *)mIconPath
                     background:(UIColor *)bcgColor;
```
######- sideMenuAddButtons
```Objective-C
/**
 Set which options to use in side menu

 @param buttons Array of PIOSideMenuButton objects of types:
 PIO_SM_EXIT_BUTTON,
 PIO_SM_SEARCH_BAR,
 PIO_SM_PRODUCTS,
 PIO_SM_FEATURED_PRODUCTS,
 PIO_SM_VIEW_CART,
 PIO_SM_SHARE_WITH_IMAGE,
 PIO_SM_EMAIL_SUPPORT
 PIO_SM_HELP
 PIO_SM_CHANGE_CURRENCY,
 PIO_SM_CHANGE_COUNTRY,
 PIO_SM_CHANGE_LANGUAGE
 
 @param optionsTitle Title for this section
 @param oTitleColor Title color
 @param optionsColor Background color for this section
 @param accountsTitle Title for this section
 @param aTitleColor Title color
 @param accountsColor Background color for this section
 
 @param info Array of PIOSideMenuButton objects of types:
 PIO_SM_PRICING_CHART,
 PIO_SM_SHARE_APP,
 PIO_SM_LIKE_US_FB,
 PIO_SM_RATE_APP,
 PIO_SM_ABOUT,
 PIO_SM_HOW_IT_WORKS,
 PIO_SM_PAST_ORDERS
 
 @param infoTitle Title for this section
 @param infoTitleColor Title color
 @param infoColor Background color for this section
 @param backgroundImageForButtons Path to file
 
 */
- (void)sideMenuAddButtons:(NSArray *)buttons
                   options:(NSArray *)options
              optionsTitle:(NSString *)optionsTitle
         optionsTitleColor:(UIColor *)oTitleColor
              optionsColor:(UIColor *)optionsColor
             accountsTitle:(NSString *)accountsTitle
        accountsTitleColor:(UIColor *)aTitleColor
             accountsColor:(UIColor *)accountsColor
                      info:(NSArray *)info
                 infoTitle:(NSString *)infoTitle
            infoTitleColor:(UIColor *)iTitleColor
                 infoColor:(UIColor *)infoColor
 backgroundImageForButtons:(NSString *)path;
```
######- sideMenuHideOptionsHeader
```Objective-C
/**
 Hide 'Options' header in Side Menu
 */
- (void)sideMenuHideOptionsHeader:(BOOL)set;
```
######- sideMenuHideAccountsHeader
```Objective-C
/**
 Hide 'Accounts' header in Side Menu
 */
- (void)sideMenuHideAccountsHeader:(BOOL)set;
```
######- sideMenuHideInfoHeader
```Objective-C
/**
 Hide 'Info' header in Side Menu
 */
- (void)sideMenuHideInfoHeader:(BOOL)set;
```
######- sideMenuShowOptionsAsList
```Objective-C
/**
 Show 'Options' section as a list

 @param set Default value is NO
 */
- (void)sideMenuShowOptionsAsList:(BOOL)set;
```
######- slideSideMenuFromRight
```Objective-C
/**
 Slide side menu from right. Default value is NO.

 @param set Default value is NO.
 */
- (void)slideSideMenuFromRight:(BOOL)set;
```
######- setShareText:additionalText
```Objective-C
/**
 This is option from Side Menu, in order to use it, Side Menu needs to be enabled first.

 @param shareText Text that will be used for sharing. May contains link also.
 @param additionalText Text used when sharing with image.
 */
- (void)setShareText:(NSString *)shareText additionalText:(NSString *)additionalText;
```
######- hidePhotoSourcesInSideMenu
```Objective-C
/**
 Hide photo sources section in Side Menu

 @param set Default value is NO
 */
- (void)hidePhotoSourcesInSideMenu:(BOOL)set;
```
######- sideMenuBackgroungImage
```Objective-C
/**
 Set background image on Side Menu

 @param path Image path
 */
- (void)sideMenuBackgroungImage:(NSString *)path;
```