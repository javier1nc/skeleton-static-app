<script lang="ts">
import { Modal, getModalStore } from '@skeletonlabs/skeleton';
import type { ModalSettings, ModalComponent, ModalStore } from '@skeletonlabs/skeleton';

const modalStore = getModalStore();


const modal: ModalSettings = {
    type: 'alert',
    // Data
    title: 'Example Alert',
    body: 'This is an example modal.',
    image: 'https://i.imgur.com/WOgTG96.gif',
};



function modalHelpTrigger(): void {
    modalStore.trigger(modal);
}
</script>

:Modal:

<button class="btn variant-filled" on:click={modalHelpTrigger}>
    <span class="indent-1">Clck</span>
</button>