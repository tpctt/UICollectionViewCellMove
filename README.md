# UICollectionViewCellMove
UICollectionViewCell长按重排
文件名称 UICollectionView+TLCellRearrange

````

@protocol UICollectionViewCellRearrangeDelegate <NSObject>

@optional

- (BOOL)collectionView:(nonnull UICollectionView *)collectionView
        shouldMoveCell:(nonnull UICollectionViewCell *)cell
           atIndexPath:(nonnull NSIndexPath *)indexPath;

- (void)collectionView:(nonnull UICollectionView *)collectionView
           putDownCell:(nonnull UICollectionViewCell *)cell
           atIndexPath:(nonnull NSIndexPath *)indexPath;

- (BOOL)collectionView:(nonnull UICollectionView *)collectionView
        shouldMoveCell:(nonnull UICollectionViewCell *)cell
         fromIndexPath:(nonnull NSIndexPath *)fromIndexPath
           toIndexPath:(nonnull NSIndexPath *)toIndexPath;

- (void)collectionView:(nonnull UICollectionView *)collectionView
           didMoveCell:(nonnull UICollectionViewCell *)cell
         fromIndexPath:(nonnull NSIndexPath *)fromIndexPath
           toIndexPath:(nonnull NSIndexPath *)toIndexPath;

@end

@interface UICollectionView (TLCellRearrange)

@property (nonatomic, weak) id<UICollectionViewCellRearrangeDelegate> _Nullable rearrangeDelegate;

@property (nonatomic, assign) BOOL enableRearrangement;

/**
 *  长按cell接触边缘时collectionView自动滚动的速率，每1/60秒移动的距离
 */
@property (nonatomic, assign) CGFloat autoScrollSpeed;

/**
 *  长按放大倍数
 *  默认为1.2
 */
@property (nonatomic, assign) CGFloat longPressMagnificationFactor;

@end
````
