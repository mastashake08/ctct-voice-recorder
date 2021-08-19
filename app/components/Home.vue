<template>
    <Page>
        <ActionBar>
            <Label :text="actionBarTitle"/>
        </ActionBar>

        <StackLayout>
            <Label class="info">
                <FormattedString>
                    <Span class="fas" text.decode="&#xf135; "/>
                    <Span :text="message"/>
                </FormattedString>
            </Label>
            <Button :text="recordingButtonText" @tap="startRecording" />
        </StackLayout>
    </Page>
</template>

<script>
  export default {
    data () {
      return {
        actionBarTitle: 'My Recording App!',
        isRecording: false
      }
    },
    methods: {
      startRecording () {
        alert('DO SOMETHING')
      }
    },
    computed: {
      message() {
        return Date.now().toString() + '.wav';
      },
      recordingButtonText () {
        return this.isRecording ? 'Stop Recording' : 'Start Recording'
      }
    }
  };
</script>

<style scoped lang="scss">
    @import '@nativescript/theme/scss/variables/blue';

    // Custom styles
    .fas {
        @include colorize($color: accent);
    }

    .info {
        font-size: 20;
        horizontal-align: center;
        vertical-align: center;
    }
</style>
