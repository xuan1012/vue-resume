<template>
    <div class="context-list" :class="{ 'icon-margin-bottom': icon }">
        <div class="list-heading" :class="{ 'icon-class': icon }">
            <div class="title">
                <EditImage v-if="icon" :src="icon" height="36" width="36" class="img"/>
                <h2 class="title" contenteditable="false">{{title}}</h2>
            </div>
            <!--            <div class="button add" @click="add" :class="{ 'icon-margin-right': icon }">+</div>-->
        </div>
        <ul id="luo">
            <ListItemAbout v-if="title === '个人技能'" v-for="item in arry" :key="item.id"/>
            <ListItemSkill v-if="title === 'Skill'" v-for="item in arry" :key="item.id"/>
            <ListItemEducation v-if="title == '教育经历'" v-for="item in arry" :key="item.id"/>
            <ListItemExperience v-if="title == '工作经历'" v-for="item in arry" :key="item.id"/>
            <ListItemInfo v-if="icon" v-for="item in arry" :key="item.id"/>
            <slot name="listItem"></slot>
        </ul>
    </div>
</template>
<script>
    import EditImage from '@/components/edit-image'
    import ListItemAbout from '@/components/list-item-about'
    import ListItemSkill from '@/components/list-item-skill'
    import ListItemEducation from '@/components/list-item-education'
    import ListItemExperience from '@/components/list-item-experience'
    import ListItemInfo from '@/components/list-item-info'

    export default {
        name: 'ContextList',
        components: {
            EditImage,
            ListItemAbout,
            ListItemSkill,
            ListItemEducation,
            ListItemExperience,
            ListItemInfo
        },
        props: {
            title: {
                type: String,
                default: 'Title'
            },
            icon: {
                type: String,
                default: ''
            }
        },
        data () {
            return {
                arry: []
            }
        },
        methods: {
            showAdd () {
                this.add = true
            },
            add () {
                this.arry.push(1)
            }
        }
    }
</script>
<style lang="less">
    .context-list {
        width: 100%;
        margin-bottom: 30px;

        .list-heading {
            display: flex;
            justify-content: space-between;
            align-items: center;

            .title {
                display: flex;
                align-items: center;
                color: #8592D6;

                .img {
                    margin: 0 20px 0 50px;
                }
            }

            &:hover .add {
                display: block;
            }

            .add {
                display: none;
            }

            .button {
                width: 30px;
                height: 30px;
                line-height: 30px;
                text-align: center;
                font-size: 24px;
                border-radius: 50%;
                background: none;
                border: 1px solid #dad8d7;
                cursor: pointer;

                &:hover {
                    background: #f2f2f2;
                }
            }
        }
    }

    .icon-class {
        background-color: #f6f7f7;
        border-bottom: 1px solid #e9e8e8;
    }

    .icon-margin-bottom {
        margin-bottom: 0;
    }

    .icon-margin-right {
        margin-right: 15px;
    }
</style>
