# MosaicLayoutDemo
![img](/pp.gif)

### Code
```swift
        let sItem1 = NSCollectionLayoutItem(layoutSize: .init(widthDimension: .fractionalWidth(0.5), heightDimension: .fractionalHeight(1)))
        sItem1.contentInsets.trailing = 4
        let sItem2 = NSCollectionLayoutItem(layoutSize: .init(widthDimension: .fractionalWidth(0.5), heightDimension: .fractionalHeight(1)))
        sItem2.contentInsets.leading = 4
        
        let hGroupSize = NSCollectionLayoutSize(widthDimension: .fractionalWidth(1), heightDimension: .fractionalHeight(0.5))
        let hGroup = NSCollectionLayoutGroup.horizontal(layoutSize: hGroupSize, subitems: [sItem1, sItem2])
        hGroup.contentInsets.top = 4
        
        let mItem = NSCollectionLayoutItem(layoutSize: .init(widthDimension: .fractionalWidth(1), heightDimension: .fractionalHeight(0.5)))
        mItem.contentInsets.bottom = 4
        
        let vGroupSize = NSCollectionLayoutSize(widthDimension: .fractionalWidth(0.5), heightDimension: .fractionalHeight(1))
        let vGroup = NSCollectionLayoutGroup.vertical(layoutSize: vGroupSize, subitems: [mItem, hGroup])
        vGroup.contentInsets.leading = 4
        
        let lItem = NSCollectionLayoutItem(layoutSize: .init(widthDimension: .fractionalWidth(0.5), heightDimension: .fractionalHeight(1)))
        lItem.contentInsets.trailing = 4
        
        let mainHGroupSize = NSCollectionLayoutSize(widthDimension: .fractionalWidth(1), heightDimension: .fractionalWidth(1))
        let mainHGroup = NSCollectionLayoutGroup.horizontal(layoutSize: mainHGroupSize, subitems: [lItem, vGroup])
        
        let section = NSCollectionLayoutSection(group: mainHGroup)
        section.contentInsets = .init(top: 8, leading: 8, bottom: 8, trailing: 8)
        section.interGroupSpacing = 8
        
        UICollectionViewCompositionalLayout(section: section)
```
