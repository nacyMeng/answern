<template>
	<div>
		<el-radio-group v-model="isCollapse" style="margin-bottom: 20px;">
			<el-radio-button :label="false">展开</el-radio-button>
			<el-radio-button :label="true">收起</el-radio-button>
		</el-radio-group>
		<el-menu default-active="/cs/register" class="el-menu-vertical-demo" :router="true" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
			<el-menu-item index="/home">
				<i class="el-icon-setting"></i>
				<span slot="title">首页</span>
			</el-menu-item>
			<el-submenu index="/cs">
				<template slot="title">
					<i class="el-icon-location"></i>
					<span slot="title" title="保全">保全</span>
				</template>
				<el-menu-item-group>
					<el-menu-item index="/cs/register">
						<span title="注册">注册</span>
					</el-menu-item>
					<el-menu-item index="/cs/entry">
						<span title="录入">录入</span>
					</el-menu-item>
					<el-menu-item index="/cs/approve">
						<span title="审核">审核</span>
					</el-menu-item>
				</el-menu-item-group>
			</el-submenu>

			<el-submenu index="/clm">
				<template slot="title">
					<i class="el-icon-menu"></i>
					<span slot="title" title="理赔">理赔</span>
				</template>
				<el-menu-item-group>
					<el-menu-item index="/claim/registration/registercase">
						<span title="报案">报案</span>
					</el-menu-item>
					<el-menu-item index="/claim/mytask">
						<span title="我的任务">我的任务</span>
					</el-menu-item>
					<el-menu-item index="/cs/approve">
						<span title="管理列表">管理列表</span>
					</el-menu-item>
				</el-menu-item-group>
			</el-submenu>
		</el-menu>
	</div>
</template>

<script>
export default {
  data() {
    return {
      isCollapse: false
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>

<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
.el-submenu span,
.el-menu-item span {
  width: 110px;
  display: inline-block;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.el-menu {
  text-align: left;
}
</style>
