# AppBar

## 简述

AppBar简单来说就是以前ActionBar进化而来，更高级，更灵活的导航栏控件，和普通的控件一样使用，但是又独成一派，有着自己的许多特性

## 组成

由ToolBar和AppBarLayout等控件组成，并且可以替代原先的ActionBar来使用

## 特点

特殊的控件，因此在主题定义的时候，可以单独定义actionBarStyle，从而可以统一各个界面的风格

## 坑

曾经遇到一次，在界面中间位置使用了AppBarLayout，准备修改过度绘制的问题，但是发现这个appBar默认加了个不一样的背景色，导致过度绘制，但是由于放在了屏幕中间，当作一个控件来使用，这就产生了很大的迷惑性，总是把这个AppBarLayout当作一个控件来思考，实际上AppBarLayout在创建时，会有自己的一套独立的设置主题的内容，因此不能简单的作为控件使用，要根据界面的特性来使用合适的控件，AppBarLayout应该作为专门的导航栏使用，其他中间位置，应该谨慎使用。