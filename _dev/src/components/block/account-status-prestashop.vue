<!--**
 * 2007-2019 PrestaShop and Contributors
 *
 * NOTICE OF LICENSE
 *
 * This source file is subject to the Academic Free License 3.0 (AFL-3.0)
 * that is bundled with this package in the file LICENSE.txt.
 * It is also available through the world-wide-web at this URL:
 * https://opensource.org/licenses/AFL-3.0
 * If you did not receive a copy of the license and are unable to
 * obtain it through the world-wide-web, please send an email
 * to license@prestashop.com so we can send you a copy immediately.
 *
 * @author    PrestaShop SA <contact@prestashop.com>
 * @copyright 2007-2019 PrestaShop SA and Contributors
 * @license   https://opensource.org/licenses/AFL-3.0 Academic Free License 3.0 (AFL-3.0)
 * International Registered Trademark & Property of PrestaShop SA
 *-->
<template>
  <div>
    <template v-if="prestashopAccountIsActive">
      <b-badge variant="success">
        {{ $t('pages.accounts.approved') }}
      </b-badge>
    </template>
    <template v-else>
      <b-badge variant="warning">
        {{ $t('pages.accounts.approvalPending') }}
      </b-badge>
    </template>
  </div>
</template>

<script>
  export default {
    name: 'AccountStatusPrestaShop',
    computed: {
      prestashopAccountIsActive() {
        return this.$store.state.firebase.onboardingCompleted;
      },
    },
  };
</script>
