# UEditor集成vue

1、在vue集成UEditor时，我们要先看一下自己使用vue的版本，**如果版本不一致那么配置也不一样**，在这里只**演示vue-cli.3.0版本**的 
    
2、首先要创建一个vue项目：vue create vue-u   
   
3、然后我们要去下载[UEditor](https://github.com/HaoChuan9421/vue-ueditor-wrap/tree/master/assets/downloads)，**切记尽量下载百度的UEditor，BUG太多还要自己去解决**

![图片](img/1.png)

4、在vue-u项目中install，UEditor
	
		$ npm i vue-ueditor-wrap

![](img/2.png)


5、在第三步中我们下载了，utf8-jsp后我们进行一个解压，然后将utf-jsp改一下名字改为UEditor，要把UEDitor复制到**public**目录下，不需要修改任何东西

![](img/3.png)

6、引用UEditor到vue中，在**App.vue**文件中写

		<template>
			<div id="app">
				<VueUeditorWrap :config="myConfig"></VueUeditorWrap>
				<div>
					<button type="primary" ></button>
				</div>
			</div>
		</template>
		
		<script>
			//导入组件
			import VueUeditorWrap from 'vue-ueditor-wrap'
			
			export default {
				name: 'app',
				data() {
					return {
						//配置富文本框
						myConfig: {
							// 编辑器不自动被内容撑高
							autoHeightEnabled: false,
							// 初始容器高度
							initialFrameHeight: '50%',
							// 初始容器宽度
							initialFrameWidth: '80%',
							// UEditor 资源文件的存放路径，如果你使用的是 vue-cli 生成的项目，通常不需要设置该选项，vue-ueditor-wrap 会自动处理常见的情况，如果需要特殊配置，参考下方的常见问题
							//UEDITOR_HOME_URL:一定要注意如果是vue-cli.2.0版本的不是这样写的
							UEDITOR_HOME_URL:  process.env.BASE_URL + 'UEditor/'
						}
					}
				},
				components: {
					//声明组件
					VueUeditorWrap
				},
				methods: {
		
				}
			}
		</script>
		
		<style>
			#app {
				font-family: 'Avenir', Helvetica, Arial, sans-serif;
				-webkit-font-smoothing: antialiased;
				-moz-osx-font-smoothing: grayscale;
				text-align: center;
				color: #2c3e50;
				margin-top: 60px;
			}
		</style>
	
		
7、这样配置就好了，现在启动就能看到效果了  

![](img/4.png)


8、如果大家配置没有成功的话，可以去看一下[HaoChuan9421](https://github.com/HaoChuan9421/vue-ueditor-wrap)作者写的