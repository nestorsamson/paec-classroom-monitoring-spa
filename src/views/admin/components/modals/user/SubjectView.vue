<template>
    <div class=" flex-1  ">


        <div class="text-black font-semibold mt-5 px-4 flex flex-col">

            <div class="mr-10 flex">Subjects</div>
            <div class="font-thin text-xs text-gray-500 flex">{{ `School year: ${store.settings[0].school_year} Semester
                            ${store.settings[0].semester}` }}</div>

        </div>

        <div class="px-3 h-96 overflow-auto" v-if="userStore.teacherSubjects[0]">

            <ul>
                <li class="hover:bg-transparent py-0.5" v-for="subject in userStore.teacherSubjects" :key="subject.id">
                    <div class="collapse bg-white ">
                        <input type="checkbox" />

                        <div class="collapse-title   ">
                            <div class="text-lg font-semibold text-black">{{ subject.name }}</div>
                        
                            <div class="text-gray-400 text-sm ">Click to show Schedules</div>
                        </div>

                        <div class="collapse-content py-0 px-1">
                           
                            <ScheduleView :subject="subject" />

                            <AddSchedule :subject="subject" :user="userStore.selectedUser"></AddSchedule>

                        </div>

                    </div>
                </li>

            </ul>


        </div>
        <div v-else>
            <div class="text-black flex justify-center py-5"> No Subject Available</div>
        </div>

        <div onclick="my_modal_5.showModal()" @click="academicStore.getSubjects(null, store.settings[0])"
            class="absolute bottom-5 z-50 right-4 bg-stone-100 rounded-full p-2 shadow-lg cursor-pointer"><svg
                fill="#000000" width="30px" height="30px" viewBox="0 0 24 24" id="add-file-6" data-name="Flat Line"
                xmlns="http://www.w3.org/2000/svg" class="icon flat-line">
                <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
                <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
                <g id="SVGRepo_iconCarrier">
                    <path id="secondary"
                        d="M11.5,19A6.5,6.5,0,0,1,18,12.5V7L14,3H5A1,1,0,0,0,4,4V20a1,1,0,0,0,1,1h6.82A6.3,6.3,0,0,1,11.5,19Z"
                        style="fill: #2ca9bc; stroke-width: 2;"></path>
                    <path id="primary" d="M16,19h4m-2-2v4M8,13h2m4-4H8"
                        style="fill: none; stroke: #000000; stroke-linecap: round; stroke-linejoin: round; stroke-width: 2;">
                    </path>
                    <path id="primary-2" data-name="primary" d="M12,21H5a1,1,0,0,1-1-1V4A1,1,0,0,1,5,3h9l4,4v6"
                        style="fill: none; stroke: #000000; stroke-linecap: round; stroke-linejoin: round; stroke-width: 2;">
                    </path>
                </g>
            </svg></div>
    </div>
    <Modal2View>
        <AddSubjectModal :settings="store.settings[0]" />
    </Modal2View>
</template>

<script>
import Modal2View from '@/views/components/ChildModalView.vue'
import AddSubjectModal from './component/AddSubjectModal.vue'
import { useAcademicStore } from '@/store/academics'
import { useUserStore } from '@/store/users'
import AddSchedule from './component/AddSchedule.vue'
import ScheduleView from './component/ScheduleView.vue'

export default {
    props: ['store'],

    components: {
        AddSubjectModal,
        Modal2View,
        AddSchedule,
        ScheduleView
    },
    setup() {
        const userStore = useUserStore()
        const academicStore = useAcademicStore()



        return { userStore, academicStore }

    }

}
</script>

<style>
li:hover {
    @apply bg-transparent
}
</style>