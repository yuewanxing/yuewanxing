<template>
    <el-container>
        <el-aside width="250px">
            <div class="log">
                <img src="../assets/img/log.png" alt="" />
            </div>
            <el-menu
                :default-active="activeMenu"
                class="el-menu-vertical-demo"
                background-color="#121432"
                text-color="#999bb3"
                active-text-color="#fff"
                router
                @select="handleOpen"
            >
                <el-menu-item index="/overview">
                    <template #title>
                        <i class="icon icon-home"></i>
                        <span>- OVERVIEW</span>
                    </template>
                </el-menu-item>
                <el-menu-item index="/bmsDetails">
                    <template #title>
                        <i class="icon icon-details icon16"></i>
                        <span>- BMS DETAILS</span>
                    </template>
                </el-menu-item>
            </el-menu>
        </el-aside>
        <el-container>
            <el-main>
                <router-view />
            </el-main>
            <el-footer>
                <img src="../assets/img/footerLog.png" alt="" />
            </el-footer>
        </el-container>
    </el-container>
</template>
<script>
export default {
    data() {
        return {
            activeMenu: "/overview",
        };
    },
    components: {},
    created() {},
    mounted() {
        this.activeMenu = localStorage.getItem("activeMenu");
    },
    methods: {
        handleOpen(key, keyPath) {
            // console.log(key, keyPath);
            localStorage.setItem("activeMenu", key);
        },
    },
};
</script>
<style lang="less" scoped>
.el-footer {
    color: #333;
    height: 100px !important;
    display: flex;
    align-items: center;
    justify-content: center;
    img {
        height: 76px;
        display: block;
        margin: auto;
    }
}

.el-aside {
    background-color: #121432;
    .log {
        width: 80%;
        height: 160px;
        margin: 16px auto;
        img {
            width: 100%;
        }
    }
}

.el-main {
    padding: 0;
    overflow: hidden;
}

.el-menu {
    border: none;
    & > .el-menu-item {
        font-size: 14px;
        overflow: hidden;
        transition: all 0.3s ease 0s;
        display: flex;
        align-items: center;
        .icon {
            margin-right: 10px;
            display: inline-block;
            width: 18px;
            height: 18px;
        }
        .icon16 {
            width: 16px;
            height: 16px;
        }
        span {
            font-size: 14px;
            letter-spacing: 0.6px;
        }
        .icon-home {
            background: url("../assets/img/icon-home.svg") no-repeat center;
            background-size: 100%;
        }
        .icon-details {
            background: url("../assets/img/icon-details.svg") no-repeat center;
            background-size: 100%;
        }
        &::before {
            content: "";
            position: absolute;
            top: 0px;
            left: 0px;
            bottom: 100%;
            width: 4px;
            height: 56px;
            background-color: rgb(102, 114, 251);
            transition: all 0.3s ease 0s;
            transform: translateY(-56px);
        }
        &:hover {
            background: rgb(18, 20, 50) !important;
            &::before {
                transform: translateY(0);
            }
        }
    }
    .el-menu-item.is-active {
        background: #6672fb !important;
        border-radius: 0 10px 10px 0;
        color: #fff !important;
        .icon-home {
            background: url("../assets/img/icon-homeSelect.svg") no-repeat
                center;
            background-size: 100%;
        }
        .icon-details {
            background: url("../assets/img/icon-detailsSelect.svg") no-repeat
                center;
            background-size: 100%;
        }
    }
}
</style>
