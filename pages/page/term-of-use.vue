<template>
  <b-container class="bv-example-row conts">
    <b-row>
      <b-col md="12" class="page">
        <h1>Term of Use</h1>
        <p>
            This document outlines what constitutes acceptable use of the {{sitename}} web site, it's associated web services, and server infrastructure. It also covers our content moderation policy and what you can expect regarding performance and availability. If you have questions about what you are legally permitted to do with content found on this web site, please consult our Copyright Policy.
        </p>
        <h2>Access</h2>
        <p>
            This web site is intended to be accessed via standard web browser software such as the ones present on our Compatible Browsers section, and similar products via direct interaction by a human. With the exception of publicly accessible RSS feeds provided in XML format, the web site and its associated files are not meant to be accessed via any automated means such as by scripts or bots or automated applications.
        </p>
        <p>
            Be aware that if you utilize an automated means of accessing or downloading this web site, in whole or in part, your access to the site may be prevented, terminated, delayed, or slowed either temporarily or permanently, especially if you attempt to download too many large files simultaneously. This is necessary in order to protect the user-experience of the web site for those who access it in the manner envisioned by it's authors.
        </p>
        <p>
            Please understand that automated access to the site, via scripts, bots, or other similar means can have the effect of seriously degrading the performance of the web site or incurring significant additional costs to its operators without sufficient revenue generated to cover those costs. Keep in mind, that even minor infractions against this policy can have a large negative effect when combined with similar actions by other users.
        </p>
        <p>
            We ask that you respect the above guidelines so that we may continue to offer the web site as a free resource to the world. We prefer to use our resources, both human and financial, to improve and expand the features and content of the web site. Your cooperation is essential.
        </p>
        <h2>Linking</h2>
        <p>
            Direct hyperlinking to images and other large files hosted by {{sitename}} is strictly prohibited without our permission. You may of course link directly to individual HTML or XML based web pages. Direct linking to our small preview images is permitted but not guaranteed.
        </p>
        <p>
            With the exception of publicly available RSS feeds in XML format, no files or services hosted on this web site are to be integrated into any other online service or application without the expressed written permission of the operators of this web site.
        </p>
        <h2>User-submitted Content</h2>
        <p>
            {{sitename}} is a community supported web site, relying on its user community for the bulk of its primary content. Currently we accept content submissions in the form of desktop wallpapers. In order to maintain the quality of our content offerings, only a subset of submissions are selected to be published to publicly accessible portions of the web site.
        </p>
        <p>
            Some of {{sitename}}'s content may be commented on publicly, with user-submitted text appearing directly on the site, associated with the appropriate content. It is the intention of the operators and architects of this site that the commenting feature be used only for constructive feedback and other discussions directly related to the content in question. It is not to be used for personal insults, explicit or implied, off-topic discussions, racially or culturally insensitive material, sexual content, or other material not suited for a family audience including small children. Additionally, we ask that personally identifiable information not be posted to the web site, regardless of whether it pertains to yourself or another individual. Children under the age of 13 shall only post comments or other content under the supervision of a parent, guardian, or other responsible adult.
        </p>
        <p>
            We reserve the right to moderate the content posted on {{sitename}}, both during and after the submission process. The moderators may delete or edit content at any time, manually or via automated means including the use of user-generated data to determine what is and is not acceptable to our audience. Moderation criteria may vary over time.
        </p>
        <h2>Prohibited Content</h2>
        <p>
            {{sitename}} is meant to be a family-safe website, which means that we don't accept content submissions which contain pornography, adult or mature content, hate speech, content that advocates against an individual, group or organisation, content that promotes weapons ( not the hobby/movie/games content type, just the trigger happy type of content ), depictions of gratuitous violence, gore, bloodshed or gruesome images, images that promote use of drugs or drug paraphernalia, copyrighted material (content for which you don't have the necessary legal rights to display), if we receive a notice or otherwise have reason to believe that your content qualifies as such we may remove or suspend your content or account.
        </p>
        <h2>Performance</h2>
        <p>
            The operators of the web site make a reasonable attempt to maintain the availability and performance of {{sitename}} and its associated services. However, uptime and accessibility cannot be guaranteed. The web site may occasionally be inaccessible, in whole or in part, due to planned or emergency maintenance, feature upgrades, bug fixes, server migrations, hardware upgrades and failures, or simply to prevent unauthorized use, hacking, or exploitation of the web site, or its resources.
        </p>
        <h2>Disclaimer</h2>
        <p>
            {{sitename}} is a community supported website with the majority of the published content being uploaded by our user community or collected from a wide range of sources including free image repositories and websites. Although published content is believed to be authorized for sharing and personal use as desktop wallpaper either by the uploader / author or for being <a href="http://freedomdefined.org/Public_domain">Public Domain</a> / <a href="https://freedomdefined.org/Definition">Free Culture</a> licensed content, unless otherwise noted in the wallpaper description, all images on this website are copyrighted by their respective authors, therefore, if you wish to use these images for any other use you must get permission from their respective authors.
        </p>
        <h2>Liability</h2>
        <p>
            {{sitename}}, its owners, employees, contractors, and partners shall not be held legally liable or financially responsible for any loss, damage, or injury incurred as a result of the use or existence of {{sitename}}, its associated sites, content, services or infrastructure.
        </p>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>


export default {
    data() {
        return {
        sitename: ''
        }
    },
    async created() {
        this.sitename = location.hostname;
    },
    head() {
        return {
            title: 'Term of Use - ' + this.sitename,
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Term of Use for ' + this.sitename + ' website'
                }
            ]
        }
    }
}
</script>
<style>
  .page h1 {
    font-size: 2rem !important;
  }
  .page p {
    text-align: justify;
  }
  .page h2 {
    font-size: 1rem;
    font-weight: 700;
  }
</style>