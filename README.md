KenBurnsView
============

Android ImageViews are animated by Ken Burns Effect.

![](https://img.shields.io/badge/Android%20Arsenal-KenBurnsView-brightgreen.svg?style=flat)


## Demo
![Demo](https://github.com/gotokatsuya/KenBurnsView/blob/master/demo.gif)


## How to use
```java
private void initializeKenBurnsView(){
    // KenBurnsView
    final KenBurnsView kenBurnsView = (KenBurnsView) findViewById(R.id.ken_burns_view);
    // kenBurnsView.setScaleType(ImageView.ScaleType.CENTER_CROP);

    // File path, or a uri or url
    List<String> urls = Arrays.asList(SampleImages.IMAGES_URL);
    kenBurnsView.loadStrings(urls);

    // ResourceID
    //List<Integer> resourceIDs = Arrays.asList(SampleImages.IMAGES_RESOURCE);
    //kenBurnsView.loadResourceIDs(resourceIDs);

    // MIX (url & id)
    //List<Object> mixingList = Arrays.asList(SampleImages.IMAGES_MIX);
    //kenBurnsView.loadMixing(mixingList);

    // LoopViewListener
    LoopViewPager.LoopViewPagerListener listener = new LoopViewPager.LoopViewPagerListener() {
        @Override
        public View OnInstantiateItem(int page) {
            TextView counterText = new TextView(getApplicationContext());
            counterText.setText(String.valueOf(page));
            return counterText;
        }

        @Override
        public void onPageScroll(int position, float positionOffset, int positionOffsetPixels) {
        }

        @Override
        public void onPageSelected(int position) {
            kenBurnsView.forceSelected(position);
        }

        @Override
        public void onPageScrollChanged(int page) {
        }
    };

    // LoopView
    LoopViewPager loopViewPager = new LoopViewPager(this, urls.size(), listener);

    //LoopViewPager loopViewPager = new LoopViewPager(this, resourceIDs.size(), listener);

    //LoopViewPager loopViewPager = new LoopViewPager(this, mixingList.size(), listener);


    FrameLayout viewPagerFrame = (FrameLayout) findViewById(R.id.view_pager_frame);
    viewPagerFrame.addView(loopViewPager);

    kenBurnsView.setPager(loopViewPager);
}
```
You should check [sample code](https://github.com/gotokatsuya/KenBurnsView/blob/master/app/src/main/java/com/goka/sample/MainActivity.java).



## Gradle
```java
repositories {
    jcenter()
}

dependencies {
    compile 'com.github.goka.kenburnsview:library:1.0.3'
}
```

## Develop

### 1.0.4
 Easy to use


## Released

### 1.0.3
Delete unneeded resources.

### 1.0.2
Fix initializing size.

### 1.0.1
Enable to load images from res.
Enable to mix. (Enable to load images from url & res)


## iOS
[CPKenburnsSlideshowView](https://github.com/muukii0803/CPKenburnsSlideshowView)


## Detail Demo Movie
[youtube](https://youtu.be/kwZC1y0vWwg)


## Library
Thanks for 
[Glide](https://github.com/bumptech/glide)

