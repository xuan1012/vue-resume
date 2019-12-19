<template>
    <ListItem class="list-item-experience">
        <div class="heading">
            <div class="company">
                <span contenteditable="false">{{ company }}</span>
            </div>
            <div class="job">
                <span contenteditable="false">{{ job }}</span>
            </div>
            <div class="date">
                <span contenteditable="false">{{ date }}</span>
            </div>
        </div>
        <p contenteditable="false">
            <span contenteditable="false">{{ work }}</span>
        </p>
    </ListItem>
</template>
<script>
    import ListItem from '@/components/list-item'

    export default {
        name: 'ListItemExperience',
        components: {
            ListItem
        },
        props: {
            company: {
                type: String,
                default: 'Google'
            },
            job: {
                type: String,
                default: 'JAVA开发'
            },
            date: {
                type: String,
                default: '2011.9 - 2015.6'
            },
            work: {
                type: String,
                default: '工作内容'
            }
        }
    }

</script>
<style lang="less">
    .list-item-experience {
        .heading {
            font-size: 18px;
            font-weight: bold;
            display: flex;
            justify-content: space-between;
            margin-bottom: 12px;

            .company {
                width: 40%
            }

            .job {
                width: 35%;
            }

            .date {
                width: 25%;
                text-align: right;
            }
        }
    }

</style>
